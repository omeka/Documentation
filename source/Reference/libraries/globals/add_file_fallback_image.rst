.. _faddfilefallbackimage:

#####################################################################################################
``add_file_fallback_image`` — Add a fallback image for files of the given mime type or type family.
#####################################################################################################

.. versionadded:: 2.2

:doc:`Plugin-related functions </Reference/packages/Function/Plugin/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/add_file_fallback_image.rst

.. php:function:: add_file_fallback_image($mimeType, $image)

    Add a fallback image for files of the given mime type or type family.
    
    The fallback is used when there are no generated derivative images and one
    is requested (for example, by a call to file_image()).
    
    :type $mimeType: string
    :param $mimeType: The mime type this fallback is for, or the mime "prefix" it is for (video, audio, etc.)
    :type $image: string
    :param $image: The name of the image to use, as would be passed to img()

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/add_file_fallback_image.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/add_file_fallback_image.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/add_file_fallback_image.rst

