.. _fitemimagegallery:

########################################################################
``item_image_gallery`` — Get a gallery of file thumbnails for an item.
########################################################################

:doc:`Item-related functions </Reference/packages/Function/View/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/item_image_gallery.rst

.. php:function:: item_image_gallery($attrs = array(), $imageType = 'square_thumbnail', $filesShow = null, $item = null)

    Get a gallery of file thumbnails for an item.
    
    :type $attrs: array
    :param $attrs: HTML attributes for the components of the gallery, in sub-arrays for 'wrapper', 'linkWrapper', 'link', and 'image'. Set a wrapper to null to omit it.
    :type $imageType: string
    :param $imageType: The type of derivative image to display.
    :type $filesShow: bool
    :param $filesShow: Whether to link to the files/show. Defaults to null, uses 'link to file metadata' appearance option.
    :type $item: Item
    :param $item: The Item to use, the current item if omitted.
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

