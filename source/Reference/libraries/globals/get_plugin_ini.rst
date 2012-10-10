##############
get_plugin_ini
##############

*******
Summary
*******

.. include:: summary/get_plugin_ini.rst

.. php:function:: get_plugin_ini(string $pluginDirName, string $iniKeyName)

    Get specified descriptive info for a plugin from its ini file.
    
    :param string $pluginDirName: The directory name of the plugin.
    :param string $iniKeyName: The name of the key in the ini file.
    :returns: string|null The value of the specified plugin key. If the key does not exist, it returns null.

*****
Usage
*****

.. include:: usage/get_plugin_ini.rst

********
Examples
********

.. include:: examples/get_plugin_ini.rst

********
See Also
********

.. include:: see_also/get_plugin_ini.rst

