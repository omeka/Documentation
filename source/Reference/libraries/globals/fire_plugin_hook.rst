################
fire_plugin_hook
################

*******
Summary
*******

.. include:: summary/fire_plugin_hook.rst

.. php:function:: fire_plugin_hook($name, $args = Array)

    Declare the point of execution for a specific plugin hook.
    
    All plugin implementations of a given hook will be executed when this iscalled. The first argument corresponds to
    the string name of the hook. Thesecond is an associative array containing arguments that will be passed tothe plugin
    hook implementations.
    
    	               
    
    .. code-block:: php 
    
    
    	               // Calls the hook 'after_save_item' with the arguments '$item' and '$arg2'
    	               fire_plugin_hook('after_save_item', array('item' => $item, 'foo' => $arg2));
    
    :param unknown $name: 
    :param unknown $args:

*****
Usage
*****

.. include:: usage/fire_plugin_hook.rst

********
Examples
********

.. include:: examples/fire_plugin_hook.rst

********
See Also
********

.. include:: see_also/fire_plugin_hook.rst

