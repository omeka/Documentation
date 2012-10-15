#############
queue_js_file
#############

*******
Summary
*******

.. include:: summary/queue_js_file.rst

.. php:function:: queue_js_file(string|array $file, string $dir = javascripts)

    Declare that a JavaScript file or files will be used on the page.
    
    All "used" scripts will be included in the page's head. This needs to becalled either before head(), or in a
    plugin_header hook.
    
    :param string|array $file: File to use, if an array is passed, each array member will be treated like a file.
    :param string $dir: Directory to search for the file. Keeping the default is recommended.

*****
Usage
*****

.. include:: usage/queue_js_file.rst

********
Examples
********

.. include:: examples/queue_js_file.rst

********
See Also
********

.. include:: see_also/queue_js_file.rst

