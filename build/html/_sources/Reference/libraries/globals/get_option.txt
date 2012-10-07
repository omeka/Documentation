##########
get_option
##########

.. php:function:: get_option(string $name)

    Get an option from the options table.
    
    If the returned value represents an object or array, it must be unserialized by the caller before use. For example:
    <code>$object = unserialize(get_option('plugin_object'))</code>.
    
    :param string $name: The option name.
    :returns: string The option value.

*****
Usage
*****



********
Examples
********



