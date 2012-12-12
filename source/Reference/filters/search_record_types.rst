###################
search_record_types
###################



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
file, add the following::

    add_filter('search_record_types', 'my_site_search_record_types');
    function my_site_search_record_types($recordTypes)
    {
        $searchRecordTypes['Exhibit'] = __('Gallery');
        $searchRecordTypes['ExhibitPage'] = __('Artist');
        return $searchRecordTypes;
    }