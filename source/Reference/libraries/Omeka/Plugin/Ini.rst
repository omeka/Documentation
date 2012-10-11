----------------
Omeka_Plugin_Ini
----------------

.. php:class:: Omeka_Plugin_Ini

    Responsible for parsing the plugin.ini file for any given plugin.

    .. php:attr:: _pluginsRootDir
    
        Plugins directory.

    .. php:attr:: _configs
    
        Set of Zend_Config_Ini objects corresponding to each plugin.

    .. php:method:: __construct(string $pluginsRootDir)
    
        :param string $pluginsRootDir: Plugins directory.

    .. php:method:: getPluginIniValue(string $pluginDirName, string $iniKeyName)
    
        Retrieve a value in plugin.ini for a given key.
        
        Will return a null value if no value can be found in the ini file for thekey.
        
        :param string $pluginDirName: Plugin name.
        :param string $iniKeyName: INI key to retrieve.
        :returns: string|null Retrieved INI value (null if not found).

    .. php:method:: hasPluginIniFile(string $pluginDirName)
    
        Return whether a plugin has a plugin.ini file
        
        :param string $pluginDirName: Plugin name.
        :returns: boolean

    .. php:method:: getPluginIniFilePath(string $pluginDirName)
    
        Return the path to the plugin.ini file
        
        :param string $pluginDirName: Plugin name.
        :returns: string

    .. php:method:: load(Plugin $plugin)
    
        Initialize a Plugin model object with the values from the INI file.
        
        :param Plugin $plugin: The plugin model to initialize.
        :returns: void