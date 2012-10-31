###################
Element Save Filter
###################

*****
Usage
*****

Customize element texts for a particular element before validating and saving a record. This is helpful if you want to prepare form data for validation automatically, limiting the possibility of a validation error. 

``array('Save', $recordType, $elementSetName, $elementName)``

* $recordType: The type of Omeka object to filter the metadata for. Most commonly, this will be 'Item'.

* $elementSetName: The name of the element set containing the metadata field to be filtered. Possible values include 'Dublin Core' and 'Item Type Metadata'.

* $elementName: The name of the specific element within the set to be filtered. 

*****
Value
*****

``string`` $text
    The original text for the element


*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record
    The record that this text applies to. The type will be the same as the filter's ``$recordType``. 

:php:class:`Element` element
    The Element record for this text. 

********
Examples
********

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('addIsbnToDcId'=>array('Save', 'Item', 'Dublin Core', 'Identifier');
        
        public function addIsbnToId($text, $args)
        {            
            return "ISBN: $text";
        }
    }

