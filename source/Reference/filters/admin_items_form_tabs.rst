#####################
admin_items_form_tabs
#####################

*****
Usage
*****

The admin_items_form_tabs filter allows you to add, remove, or modify the tabs on the edit item form. 

*****
Value
*****

``array`` $tabs
    An array of the item form tabs. The keys are the tab names, and the values are the HTML content of each tab. A filter function should modify this array and return it.  

*********
Arguments
*********

:php:class:`Item` item
    The Item being edited. Filter functions can use this parameter to change the tabs or content on an item-by-item basis. 

********
Examples
********

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('admin_items_form_tabs');
        
        public filterAdminItemsFormTabs($tabs, $args)
        {
            $item = $args['item'];
            $tabs["My Plugin"] = uri('/my-plugin/edit/id/' . $item->id);
        }    
    }

