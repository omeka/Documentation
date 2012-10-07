################
fire_plugin_hook
################

.. php:function:: fire_plugin_hook(string $name, array $args = Array)

    Declare the point of execution for a specific plugin hook.
    
    All plugin implementations of a given hook will be executed when this is called. The first argument corresponds to
    the string name of the hook. The second is an associative array containing arguments that will be passed to the
    plugin hook implementations.
    
    .. code-block:: php 
    
         // Calls the hook 'after_save_item' with the arguments '$item' and '$arg2'
         fire_plugin_hook('after_save_item', array('item' => $item, 'foo' => $arg2));
    
    :param string $name: The hook name.
    :param array $args: Arguments to be passed to the hook implementations.
    :returns: mixed

*****
Usage
*****



********
Examples
********



