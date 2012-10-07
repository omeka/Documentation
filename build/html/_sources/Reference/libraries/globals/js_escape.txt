#########
js_escape
#########

.. php:function:: js_escape(string $value)

    Escape the value for use in javascript.
    
    This is a convenience function for encoding a value using JSON notation.
    Must be used when interpolating PHP output in javascript. Note on usage: do not wrap the resulting output of this
    function in quotes, as proper JSON encoding will take care of that.
    
    :param string $value: 
    :returns: string

*****
Usage
*****



********
Examples
********



