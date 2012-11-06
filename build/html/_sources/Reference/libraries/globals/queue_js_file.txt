.. _fqueuejsfile:

#############
queue_js_file
#############

:doc:`Head-related functions </Reference/packages/Function/View/Head/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_js_file.rst

.. php:function:: queue_js_file(string|array $file, string $dir = javascripts, array $options = Array)

    Declare that a JavaScript file or files will be used on the page.
    
    All "used" scripts will be included in the page's head. This needs to becalled either before head(), or in a plugin_header hook.
    
    :param string|array $file: File to use, if an array is passed, each array member will be treated like a file.
    :param string $dir: Directory to search for the file. Keeping the default is recommended.
    :param array $options: An array of options.

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

