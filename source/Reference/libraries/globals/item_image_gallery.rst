.. _fitemimagegallery:

##################
item_image_gallery
##################

:doc:`Item-related functions </Reference/packages/Function/View/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/item_image_gallery.rst

.. php:function:: item_image_gallery(array $attrs, string $imageType = square_thumbnail, boolean $filesShow = , Item $item)

    Get a gallery of file thumbnails for an item.
    
    :param array $attrs: HTML attributes for the components of the gallery, in sub-arrays for 'wrapper', 'linkWrapper', 'link', and 'image'. Set a wrapper to null to omit it.
    :param string $imageType: The type of derivative image to display.
    :param boolean $filesShow: Whether to link to the files/show. Defaults to false, links to the original file.
    :param Item $item: The Item to use, the current item if omitted.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/item_image_gallery.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/item_image_gallery.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/item_image_gallery.rst

