.. _flinktoitem:

############
link_to_item
############

:doc:`Link-related functions </Reference/packages/Function/View/Navigation/Link/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_item.rst

.. php:function:: link_to_item(string $text, array $props = Array, string $action = show, Item $item)

    Return a link to an item.
    
    :param string $text: HTML for the text of the link.
    :param array $props: Properties for the <a> tag.
    :param string $action: The page to link to (this will be the 'show' page almost always within the public theme).
    :param Item $item: Used for dependency injection testing or to use this function outside the context of a loop.
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

