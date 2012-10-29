#########
js_escape
#########

:doc:`Head-related functions </Reference/packages/Function/View/Head/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/js_escape.rst

.. php:function:: js_escape(string $value)

    Escape the value for use in javascript.
    
    This is a convenience function for encoding a value using JSON notation.Must be used when interpolating PHP output
    in javascript. Note on usage: donot wrap the resulting output of this function in quotes, as proper JSONencoding
    will take care of that.
    
    :param string $value: 
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

