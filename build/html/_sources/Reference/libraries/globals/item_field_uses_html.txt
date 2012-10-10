####################
item_field_uses_html
####################

*******
Summary
*******

.. include:: summary/item_field_uses_html.rst

.. php:function:: item_field_uses_html(string $elementSetName, string $elementName, integer $index = 0, Item|null $item)

    Determine whether a specific element uses HTML.
    
    By default this will test the first element text, though it is possible to test against a different element text by
    modifying the $index parameter.
    
    :param string $elementSetName: 
    :param string $elementName: 
    :param integer $index: 
    :param Item|null $item: Check for this specific item record (current item if null).
    :returns: boolean

*****
Usage
*****

.. include:: usage/item_field_uses_html.rst

********
Examples
********

.. include:: examples/item_field_uses_html.rst

********
See Also
********

.. include:: see_also/item_field_uses_html.rst

