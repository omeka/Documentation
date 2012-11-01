#########################
Element Validation Filter
#########################

*****
Usage
*****

Perform a custom validation on the texts for any particular element. 

This filter's name is actually an array of strings. The first string must always be 'Validate', but the last three can change depending on exactly what values you want to validate. 

``array('Validate', $recordType, $elementSetName, $elementName)``

* $recordType: The type of Omeka object to filter the metadata for.

* $elementSetName: The name of the element set containing the metadata field to be filtered. Possible values will include 'Dublin Core' and 'Item Type Metadata'.

* $elementName: The name of the specific element within the set to be filtered. 

*****
Value
*****

``bool`` $isValid

    Whether the element text is valid.

*********
Arguments
*********

``string``  text

    The text for the element
    
:php:class:`Omeka_Record_AbstractRecord` record

    The record (subclass of Omeka_Record_AbstractRecord) being validated.
    
:php:class:`Element` element

    The element (e.g., Dublin Core Title) for the element text.

********
Examples
********

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        protected $_filters = array('itemTitleLengthValidator' => array('Validate', 'Item', 'Dublin Core', 'Title')); 
        
        public function itemTitleValidator($isValid, $args)
        {
            $text = $args['text'];
            if(strlen($text) > 100) {
                return false;
            }
            return true;
        }
        
    }

********
See Also
********

:php:meth:`ElementText::_elementTextIsValid`
