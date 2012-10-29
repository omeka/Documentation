#############
item_citation
#############

:doc:`Item-related functions </Reference/packages/Function/View/Body/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/item_citation.rst

.. php:function:: item_citation(Item|null $item)

    Return a valid citation for the current item.
    
    Generally follows Chicago Manual of Style note format for webpages.Implementers can use the item_citation filter to
    return a customized citation.
    
    :param Item|null $item: Check for this specific item record (current item if null).
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/item_citation.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/item_citation.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/item_citation.rst

