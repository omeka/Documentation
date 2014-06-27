The ``head_js()`` helper function prints HTML script tags to the page for each script 
added with :php:func:`queue_js_file`. It is commonly used in a theme's ``common/header.php`` file to 
print the script tags inside the page head.

head_js() will also include Omeka's "default" JavaScript files. 