----------------
Omeka_Plugin_Ini
----------------

Package: :doc:`Plugin </Reference/packages/Plugin/index>`

.. php:class:: Omeka_Plugin_Ini

    Responsible for parsing the plugin.ini file for any given plugin.

    .. php:attr:: _pluginsRootDir

        protected string

        Plugins directory.

    .. php:attr:: _configs

        protected array

        Set of Zend_Config_Ini objects corresponding to each plugin.

    .. php:method:: __construct($pluginsRootDir)

        :type $pluginsRootDir: string
        :param $pluginsRootDir: Plugins directory.

    .. php:method:: getPluginIniValue($pluginDirName, $iniKeyName)

        Retrieve a value in plugin.ini for a given key.

        Will return a null value if no value can be found in the ini file for the
        key.

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :type $iniKeyName: string
        :param $iniKeyName: INI key to retrieve.
        :returns: string|null Retrieved INI value (null if not found).

    .. php:method:: hasPluginIniFile($pluginDirName)

        Return whether a plugin has a plugin.ini file

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :returns: boolean

    .. php:method:: getPluginIniFilePath($pluginDirName)

        Return the path to the plugin.ini file

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :returns: string

    .. php:method:: load(Plugin $plugin)

        Initialize a Plugin model object with the values from the INI file.

        :type $plugin: Plugin
        :param $plugin: The plugin model to initialize.
        :returns: void
