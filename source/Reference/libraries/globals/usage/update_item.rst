Valid keys for the ``$metadata`` array include:

``'item_type_id'`` : integer
    The ID of the Item Type for the Item.

``'item_type_name'`` : string
    The name of the Item Type for the Item. This option takes precedence over
    ``'item_type_id'`` if both are specified.

``'collection_id'`` : integer
    The ID of the Collection the item belongs to.

``'public'`` : integer
    Whether the Item is public (set 1 or 0).

``'featured'`` : integer
    Whether the Item is featured (set 1 or 0).

``'overwriteElementTexts'`` : mixed
    If present with any value, the element texts passed in ``$elementTexts``
    replace the existing texts instead of appending to them.


The ``$elementTexts`` array has the same format as the array passed to
:php:meth:`Mixin_ElementText::addElementTextsByArray`.
