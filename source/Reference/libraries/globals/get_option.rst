##########
get_option
##########

*******
Summary
*******

.. include:: summary/get_option.rst

.. php:function:: get_option($name)

    Get an option from the options table.
    
    If the returned value represents an object or array, it must be unserialized by the caller before use. For example:
    <code>
    $object = unserialize(get_option('plugin_object'));
    </code>
    
    :param unknown $name:

*****
Usage
*****

.. include:: usage/get_option.rst

********
Examples
********

.. include:: examples/get_option.rst

********
See Also
********

.. include:: see_also/get_option.rst

