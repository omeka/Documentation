
###################
item_search_filters
###################

*****
Usage
*****

Use this filter in conjunction with the :ref:`modelbrowsesql` hook to display what search filters are being applied to the item search.

If your plugin uses ``item_browse_sql`` to provide an additional filter when searching, you should use this filter to display the results.

Look through the ``request_array`` passed in the arguments for the key/value pair with key matching the additional filter you have created. Add the display value to the array as a new key/value pair, with the key being the name of your filter and the value being the text to display.

*****
Value
*****

``array`` $displayArray
    Array of filters for the search/browse page. Keys are possible ``$_GET`` parameters. Values are values being filtered.
    
*********
Arguments
*********

``array`` request_array
    Array of ``$_GET`` parameters
    
********
Examples
********

The MultiCollections plugin clobbers the core collection filtering message by checking if a ``multi-collection`` value is among the ``$_GET`` parameters and displaying the collection name.

.. code-block:: php

    public function filterItemSearchFilters($displayArray, $args)
    {        
        $request_array = $args['request_array'];
        if(isset($request_array['multi-collection'])) {
            $db = get_db();
            $collection = $db->getTable('Collection')->find($request_array['multi-collection']);
            $displayValue = strip_formatting(metadata($collection, array('Dublin Core', 'Title')));            
            $displayArray['collection'] = $displayValue;
        }        
        return $displayArray;
    }


********
See Also
********

:php:class:`Omeka_View_Helper_ItemSearchFilters`
        