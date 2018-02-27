.. _fjstag:

###############################################################
``js_tag`` — Get a tag for including a local JavaScript file.
###############################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/js_tag.rst

.. php:function:: js_tag($file, $dir = 'javascripts', $version = OMEKA_VERSION)

    Get a tag for including a local JavaScript file.
    
    :type $file: string
    :param $file: The name of the file, without .js extension.
    :type $dir: string
    :param $dir: The directory in which to look for javascript files. Recommended to leave the default value.
    :type $version: mixed
    :param $version: Version number. By default OMEKA_VERSION.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/js_tag.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/js_tag.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/js_tag.rst

