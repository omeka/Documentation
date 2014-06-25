.. _fqueuecssstring:

##############################################################
``queue_css_string`` — Add a CSS string to the current page.
##############################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_css_string.rst

.. php:function:: queue_css_string($string, $media = 'all', $conditional = false)

    Add a CSS string to the current page.
    
    The inline stylesheet will appear in the head element. This needs to be
    called either before head() or in a plugin_header hook.
    
    :type $string: string
    :param $string: CSS string to include.
    :type $media: string
    :param $media: CSS media declaration, defaults to 'all'.
    :type $conditional: string|bool
    :param $conditional: IE-style conditional comment, used generally to include IE-specific styles. Defaults to false.

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

