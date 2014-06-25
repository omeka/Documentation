.. _fqueuecssurl:

################################################################
``queue_css_url`` — Add a CSS file to the current page by URL.
################################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_css_url.rst

.. php:function:: queue_css_url($url, $media = 'all', $conditional = false)

    Add a CSS file to the current page by URL.
    
    The stylesheet link will appear in the head element. This needs to be
    called either before head() or in a plugin_header hook.
    
    :param $url:
    :type $media: string
    :param $media: CSS media declaration, defaults to 'all'.
    :type $conditional: string|bool
    :param $conditional: IE-style conditional comment, used generally to include IE-specific styles. Defaults to false.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/queue_css_url.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/queue_css_url.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/queue_css_url.rst

