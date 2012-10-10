#############
item_citation
#############

*******
Summary
*******

.. include:: summary/item_citation.rst

.. php:function:: item_citation(Item|null $item)

    Return a valid citation for the current item.
    
    Generally follows Chicago Manual of Style note format for webpages. 
    Implementers can use the item_citation filter to return a customized citation.
    
    :param Item|null $item: Check for this specific item record (current item if null).
    :returns: string

*****
Usage
*****

.. include:: usage/item_citation.rst

********
Examples
********

.. include:: examples/item_citation.rst

********
See Also
********

.. include:: see_also/item_citation.rst

