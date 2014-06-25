.. _fqueuejsstring:

####################################################################
``queue_js_string`` — Add a JavaScript string to the current page.
####################################################################

:doc:`Asset-related functions </Reference/packages/Function/View/Asset/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/queue_js_string.rst

.. php:function:: queue_js_string($string, $options = array())

    Add a JavaScript string to the current page.
    
    The script will appear in the head element. This needs to be called either
    before head() or in a plugin_header hook.
    
    :type $string: string
    :param $string: JavaScript string to include.
    :type $options: array
    :param $options: An array of options.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/queue_js_string.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/queue_js_string.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/queue_js_string.rst

