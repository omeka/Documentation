####################
image_tag_attributes
####################

.. versionadded:: 2.7

*****
Usage
*****

Filter the HTML attributes used for an record's image.

This filter affects ``<img>`` tags created by :php:func:`file_markup`, :php:func:`files_for_item`,
:php:func:`record_image`, :php:func:`item_image`, and :php:func:`file_image` (essentially meaning
it covers anywhere derivative images are used for a record).

*****
Value
*****

``array`` $attrs
    Array of HTML attributes for the ``<img>`` tag.
    
*********
Arguments
*********

:php:class:`Omeka_Record` record
    The record being displayed (could be an Item or Collection in the case of a thumbnail)
    
:php:class:`File` file
    The file being displayed. This is always the File that directly corresponds with the
    image, while ``record`` can be another record like an Item, Collection or Exhibit
    that simply uses the File as its representative image.
    
``string`` format
    Type of derivative image being displayed (e.g., ``'thumbnail'``, ``'fullsize'``, ``'square_thumbnail'``)
    
            
