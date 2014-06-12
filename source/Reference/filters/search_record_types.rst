###################
search_record_types
###################

*****
Usage
*****

Add a record type to the list of options for the search form. Plugins that add searchable content 
should use this to allow administrators to choose whether to include that content in the search options.

*****
Value
*****

``array`` $searchRecordTypes
   A key-value array where keys are names of record types and values are the internationalized
   forms of their labels::

      $searchRecordTypes = array(
          'Item'       => __('Item'), 
          'File'       => __('File'), 
          'Collection' => __('Collection'), 
      );


*********
Arguments
*********

None

********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        /**
         * Add SimplePagesPage as a searchable type.
         */
        function filterSearchRecordTypes($recordTypes)
        {
            $recordTypes['SimplePagesPage'] = __('Simple Page');
            return $recordTypes;
        }    
    }

There are times when theme writers will want to change the record type label on 
the search results page. For example, when the "Exhibit" is a gallery and the 
"Exhibit Pages" are individual artists. To do this, in the theme's custom.php 
file, add the following

.. code-block:: php

    add_filter('search_record_types', 'my_site_search_record_types');
    function my_site_search_record_types($recordTypes)
    {
        $searchRecordTypes['Exhibit'] = __('Gallery');
        $searchRecordTypes['ExhibitPage'] = __('Artist');
        return $searchRecordTypes;
    }
    
********
See also
********

:php:func:`get_search_record_types`
 
