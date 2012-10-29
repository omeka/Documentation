################
queue_css_string
################

:doc:`Head-related functions </Reference/packages/Function/View/Head/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_css_string.rst

.. php:function:: queue_css_string(string $string, string $media = all, string|bool $conditional = )

    Declare a CSS string to be used on the page and included in the page's head.
    
    This needs to be called either before head() or in a plugin_header hook.
    
    :param string $string: CSS string to include.
    :param string $media: CSS media declaration, defaults to 'all'.
    :param string|bool $conditional: IE-style conditional comment, used generally to include IE-specific styles. Defaults to false.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/queue_css_string.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/queue_css_string.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/queue_css_string.rst

