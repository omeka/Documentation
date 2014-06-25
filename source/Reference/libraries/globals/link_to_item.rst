.. _flinktoitem:

###########################################
``link_to_item`` — Get a link to an item.
###########################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_item.rst

.. php:function:: link_to_item($text = null, $props = array(), $action = 'show', $item = null)

    Get a link to an item.
    
    The only differences from link_to are that this function will
    automatically use the "current" item, and will use the item's title as the
    link text.
    
    :type $text: string
    :param $text: HTML for the text of the link.
    :type $props: array
    :param $props: Properties for the <a> tag.
    :type $action: string
    :param $action: The page to link to (this will be the 'show' page almost always within the public theme).
    :type $item: Item
    :param $item: Used for dependency injection testing or to use this function outside the context of a loop.
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_item.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_item.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_item.rst

