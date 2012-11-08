######################
Element Display Filter
######################

*****
Usage
*****

Alter the way an element is displayed.

The name of the filter is an array:

.. code-block:: php

    array('Display', $recordType, $elementSetName, $elementName);

* $recordType: The type of Omeka object to filter the metadata for. Most commonly, this will be 'Item'.

* $elementSetName: The name of the element set containing the metadata field to be filtered. Possible values include 'Dublin Core' and 'Item Type Metadata'.

* $elementName: The name of the specific element within the set to be filtered. 

*****
Value
*****

``string`` $text
    The text to display.

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record
    The record being displayed

:php:class:`ElementText` element_text
    The ElementText object

********
Examples
********

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        protected $_filters = array('concealDescription', array('Display', 'Item', 'Dublin Core', 'Description));
    
        public function concealDescription($text, $args)
        {
            //conceal the description to non-logged in users
            if(!get_current_user()) {
                return str_rot12($text);
            }
            return $text;
        }    
    }

