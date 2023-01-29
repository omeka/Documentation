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

    In 2.7 and later, the initial filter passes ``false`` here, and returning
    ``false`` from the filter will cause Omeka to use the default "previous" item.
    Returning ``null`` will indicate there is no previous item (that the current
    record is the first one in the sequence).

    From 2.5 through 2.6, the initial filter passes ``null`` here, and returning
    any "falsy" value will cause Omeka to use the default "previous" item. In these
    versions, this filter cannot indicate the start of the sequence.

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


