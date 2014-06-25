.. _fqueuejsfile:

###############################################################################
``queue_js_file`` — Add a local JavaScript file or files to the current page.
###############################################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_js_file.rst

.. php:function:: queue_js_file($file, $dir = 'javascripts', $options = array())

    Add a local JavaScript file or files to the current page.
    
    All scripts will be included in the page's head. This needs to be called
    either before head(), or in a plugin_header hook.
    
    :type $file: string|array
    :param $file: File to use, if an array is passed, each array member will be treated like a file.
    :type $dir: string
    :param $dir: Directory to search for the file. Keeping the default is recommended.
    :type $options: array
    :param $options: An array of options.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/queue_js_file.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/queue_js_file.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/queue_js_file.rst

