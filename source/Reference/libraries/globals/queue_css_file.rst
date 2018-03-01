.. _fqueuecssfile:

###################################################################
``queue_css_file`` — Add a CSS file or files to the current page.
###################################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_css_file.rst

.. php:function:: queue_css_file($file, $media = 'all', $conditional = false, $dir = 'css', $version = OMEKA_VERSION)

    Add a CSS file or files to the current page.
    
    All stylesheets will be included in the page's head. This needs to be
    called either before head(), or in a plugin_header hook.
    
    :type $file: string|array
    :param $file: File to use, if an array is passed, each array member will be treated like a file.
    :type $media: string
    :param $media: CSS media declaration, defaults to 'all'.
    :type $conditional: string|bool
    :param $conditional: IE-style conditional comment, used generally to include IE-specific styles. Defaults to false.
    :type $dir: string
    :param $dir: Directory to search for the file.  Keeping the default is recommended.
    :type $version: mixed
    :param $version: Version number. By default OMEKA_VERSION.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/queue_css_file.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/queue_css_file.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/queue_css_file.rst

