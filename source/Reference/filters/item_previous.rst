#############
item_previous
#############

.. versionadded:: 2.5

*****
Usage
*****

Replaces the item returned by :php:meth:`Item::previous()`, and therefore also
the item linked to by the "Previous Item" link on the item show page.

*****
Value
*****

``Item`` $previousItem
    The "previous" item relative to the one passed as the ``item`` argument.
    Note, the initial filter passes `null` here. Returning `null` will
    cause Omeka to use the default "previous" item.

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

:doc:`item_next`


