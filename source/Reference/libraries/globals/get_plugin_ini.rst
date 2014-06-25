.. _fgetpluginini:

#####################################################################################
``get_plugin_ini`` — Get specified descriptive info for a plugin from its ini file.
#####################################################################################

:doc:`Plugin-related functions </Reference/packages/Function/Plugin/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_plugin_ini.rst

.. php:function:: get_plugin_ini($pluginDirName, $iniKeyName)

    Get specified descriptive info for a plugin from its ini file.
    
    :type $pluginDirName: string
    :param $pluginDirName: The directory name of the plugin.
    :type $iniKeyName: string
    :param $iniKeyName: The name of the key in the ini file.
    :returns: string|null The value of the specified plugin key. If the key does not exist, it returns null.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_plugin_ini.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_plugin_ini.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_plugin_ini.rst

