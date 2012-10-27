##############
queue_css_file
##############

:doc:`Head-related functions </Reference/packages/Function/View/Head/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_css_file.rst

.. php:function:: queue_css_file(string|array $file, string $media = all, string|bool $conditional = , string $dir = css)

    Declare that a CSS file or files will be used on the page.
    
    All "used" stylesheets will be included in the page's head. This needs to becalled either before head(), or in a
    plugin_header hook.
    
    :param string|array $file: File to use, if an array is passed, each array member will be treated like a file.
    :param string $media: CSS media declaration, defaults to 'all'.
    :param string|bool $conditional: IE-style conditional comment, used generally to include IE-specific styles. Defaults to false.
    :param string $dir: Directory to search for the file.  Keeping the default is recommended.

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

