.. globals.

#############
Theme Helpers
#############


.. php:function:: get_option($name)

     Get an option from the options table.
    
     If the returned value represents an object or array, it must be unserialized
     by the caller before use. For example:
     
     .. code-block:: php
        
        $object = unserialize(get_option('plugin_object'));
     
     :param string $name: The option name
     
     :returns: string The option value
     
     See also: :php:func:`set_option`
     
     
.. php:function:: set_option($name, $value)

     Set an option to the options table.
    
     .. note::
     
        Objects and arrays must be serialized before being saved.
    
     :param string $name:  The option name
     
     :param string $value:  The option value
     
     See also: :php:func:`get_option`
