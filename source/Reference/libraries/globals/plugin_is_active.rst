################
plugin_is_active
################

.. php:function:: plugin_is_active(string $name, string $version, string $compOperator = >=)

    Determine whether a plugin is installed and active.
    
    May be used by theme/plugin writers to customize behavior based on the existence of certain plugins. Some examples
    of how to use this function:
    
    Check if ExhibitBuilder is installed and activated.
    <code>if (plugin_is_active('ExhibitBuilder')):</code>
    
    Check if installed version of ExhibitBuilder is at least version 1.0 or higher.
    <code>if (plugin_is_active('ExhibitBuilder', '1.0')):</code>
    
    Check if installed version of ExhibitBuilder is anything less than 2.0.
    <code>if (plugin_is_active('ExhibitBuilder', '2.0', '<')):</code>
    
    :param string $name: Directory name of the plugin.
    :param string $version: Version of the plugin to check.
    :param string $compOperator: Comparison operator to use when checking the installed version of ExhibitBuilder.
    :returns: boolean

*****
Usage
*****



********
Examples
********



