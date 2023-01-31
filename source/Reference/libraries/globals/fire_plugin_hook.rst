.. _ffirepluginhook:

###################################################################################
``fire_plugin_hook`` — Declare the point of execution for a specific plugin hook.
###################################################################################

:doc:`Plugin-related functions </Reference/packages/Function/Plugin/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/fire_plugin_hook.rst

.. php:function:: fire_plugin_hook($name, array $args = array())

    Declare the point of execution for a specific plugin hook.
    
    All plugin implementations of a given hook will be executed when this is
    called. The first argument corresponds to the string name of the hook. The
    second is an associative array containing arguments that will be passed to
    the plugin hook implementations.
    
    <code>
    // Calls the hook 'after_save_item' with the arguments '$item' and '$arg2'
    fire_plugin_hook('after_save_item', array('item' => $item, 'foo' =>
    $arg2));
    </code>
    
    :type $name: string
    :param $name: The hook name.
    :type $args: array
    :param $args: Arguments to be passed to the hook implementations.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/fire_plugin_hook.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/fire_plugin_hook.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/fire_plugin_hook.rst

