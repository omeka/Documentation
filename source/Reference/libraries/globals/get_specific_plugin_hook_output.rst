.. _fgetspecificpluginhookoutput:

###############################################################################################
``get_specific_plugin_hook_output`` — Get the output of a specific plugin's hook as a string.
###############################################################################################

:doc:`Plugin-related functions </Reference/packages/Function/Plugin/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_specific_plugin_hook_output.rst

.. php:function:: get_specific_plugin_hook_output($pluginName, $hookName, $args = array())

    Get the output of a specific plugin's hook as a string.
    
    This is like get_plugin_hook_output() but only calls the hook within the
    provided plugin.
    
    :type $pluginName: string
    :param $pluginName: Directory name of the plugin to execute the hook for.
    :type $hookName: string
    :param $hookName: Name of the hook to fire.
    :type $args: mixed
    :param $args: Any arguments to be passed to the hook implementation.
    :returns: string|null

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_specific_plugin_hook_output.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_specific_plugin_hook_output.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_specific_plugin_hook_output.rst

