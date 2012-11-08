
#####################
ElementSetForm_Filter
#####################

*****
Usage
*****

Filters the form to be used for an element set

The name of the filter is an array:

.. code-block:: php

    array('ElementSetForm', $recordType, $elementSet, $elementName);

* $recordType: The type of Omeka object to filter the metadata for. Most commonly, this will be 'Item'.

* $elementSetName: The name of the element set containing the metadata field to be filtered. Possible values include 'Dublin Core' and 'Item Type Metadata'.

* $elementName: The name of the specific element within the set to be filtered. 


*****
Value
*****

``array`` $elements
    Array of :php:class:`Element`s to filter


*********
Arguments
*********

``string`` recordType
    The type of record
    
:php:class:`Omeka_Record_AbstractRecord` record
    The record whose form is being filtered
    
``string`` elementSetName
    The name of the element set whose elements should be filtered

********
Examples
********


********
See Also
********

