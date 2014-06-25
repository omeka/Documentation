.. _fjsescape:

#######################################################
``js_escape`` — Escape a value for use in javascript.
#######################################################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/js_escape.rst

.. php:function:: js_escape($value)

    Escape a value for use in javascript.
    
    This is a convenience function for encoding a value using JSON notation.
    Must be used when interpolating PHP output in javascript. Note on usage:
    do not wrap the resulting output of this function in quotes, as proper
    JSON encoding will take care of that.
    
    :type $value: string
    :param $value:
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/js_escape.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/js_escape.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/js_escape.rst

