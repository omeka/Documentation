##############
item_thumbnail
##############

*******
Summary
*******

.. include:: summary/item_thumbnail.rst

.. php:function:: item_thumbnail(array $props = Array, integer $index = 0, Item $item)

    Return HTML for a thumbnail image assigned to an item.
    
    Default parameters will use the first image, but that can be changed by modifying $index.
    
    :param array $props: A set of attributes for the <img /> tag.
    :param integer $index: The position of the file to use (starting with 0 for the first file).
    :param Item $item: The item to which the image belongs
    :returns: string HTML

*****
Usage
*****

.. include:: usage/item_thumbnail.rst

********
Examples
********

.. include:: examples/item_thumbnail.rst

********
See Also
********

.. include:: see_also/item_thumbnail.rst

