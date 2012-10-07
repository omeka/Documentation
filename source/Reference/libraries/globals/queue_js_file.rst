#############
queue_js_file
#############

.. php:function:: queue_js_file(string|array $file, string $dir = javascripts)

    Declare that a JavaScript file or files will be used on the page.
    
    All "used" scripts will be included in the page's head. This needs to be called either before head(), or in a
    plugin_header hook.
    
    :param string|array $file: File to use, if an array is passed, each array member will be treated like a file.
    :param string $dir: Directory to search for the file. Keeping the default is recommended.

*****
Usage
*****



********
Examples
********



