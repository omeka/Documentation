######################
Element Flatten Filter
######################

*****
Usage
*****

'Flatten' the array of data for an element into the text to use.

The array looks like:

.. code-block:: php

    array('text' => 'The text', 'html'=>0);
    
Where the ``html`` key is a boolean for whether the element text uses HTML.    

If no Element Flatten filters operate, the value of the ``text`` key is used.

This filter's name is actually an array of strings. The first string must always be 'Flatten', but the last three can change depending on exactly what values you want to filter.

``array('Flatten', $recordType, $elementSetName, $elementName)``

* $recordType: The type of Omeka object to filter the metadata for.

* $elementSetName: The name of the element set containing the metadata field to be filtered. Possible values will include 'Dublin Core' and 'Item Type Metadata'.

* $elementName: The name of the specific element within the set to be filtered. 


*****
Value
*****

``string`` $flatText
    The flattened text to return. Initially ``null``.

*********
Arguments
*********

``array`` post_array
    The posted data, like ``array('text' => 'The text', 'html'=>0);``
    
:php:class:`Element` element
    The element being saved.

********
Examples
********

.. code-block:: php

    $_filters = array('prependJulianToDate' => array('Flatten', 'Item', 'Dublin Core', 'Date'));

    public function prependJulianToDate($flatText, $args)
    {
        $postArray = $args['post_array'];
        $value = $postArray['text'];
        return "Julian Calendar: $value";
    }

********
See Also
********

:php:meth:`ElementText::getTextStringFromFormPost`
