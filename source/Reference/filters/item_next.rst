#########
item_next
#########

.. versionadded:: 2.5

*****
Usage
*****

Replaces the item returned by :php:meth:`Item::next()`, and therefore also
the item linked to by the "Next Item" link on the item show page.

*****
Value
*****

``Item`` $nextItem
    The "next" item relative to the one passed as the ``item`` argument.
    Note, the initial filter passes `null` here. Returning `null` will
    cause Omeka to use the default "next" item.

*********
Arguments
*********

:php:class:`Item` item
    The current item

********
Examples
********


********
See Also
********

:doc:`item_previous`


