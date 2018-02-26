-------------------
Omeka_Plugin_Loader
-------------------

Package: :doc:`Plugin\\Loader </Reference/packages/Plugin/Loader/index>`

.. php:class:: Omeka_Plugin_Loader

    Loads plugins for any given request.

    This will iterate through the plugins root directory and load all plugin.php files by require()'ing them.

    .. php:attr:: _broker

        protected Omeka_Plugin_Broker

        Plugin broker object.

    .. php:attr:: _iniReader

        protected Omeka_Plugin_Ini

        Plugin INI reader object.

    .. php:attr:: _mvc

        protected Omeka_Plugin_Mvc

        Plugin MVC object.

    .. php:attr:: _basePath

        protected string

        Plugins directory.

    .. php:attr:: _plugins

        protected array

        An array of all plugins (installed or not) that are currently located
        in the plugins/ directory.

    .. php:method:: __construct(Omeka_Plugin_Broker $broker, Omeka_Plugin_Ini $iniReader, Omeka_Plugin_Mvc $mvc, $pluginsBaseDir)

        :type $broker: Omeka_Plugin_Broker
        :param $broker: Plugin broker.
        :type $iniReader: Omeka_Plugin_Ini
        :param $iniReader: plugin.ini reader.
        :type $mvc: Omeka_Plugin_Mvc
        :param $mvc: Plugin MVC object.
        :type $pluginsBaseDir: string
        :param $pluginsBaseDir: Plugins directory.

    .. php:method:: loadPlugins($plugins, $force = false)

        Load a list of plugins.

        :type $plugins: array
        :param $plugins: List of Plugin records to load.
        :type $force: bool
        :param $force: If true, throws exceptions for plugins that cannot be loaded for some reason.

    .. php:method:: registerPlugin(Plugin $plugin)

        Register a plugin so that it can be accessed by other plugins (if
        necessary)
        during the load process.

        There should only be a single instance of a plugin per directory name.
        Registering a plugin more than once, i.e. loading a plugin again after the
        first time failed, will not cause a problem as long as the same instance
        was registered.

        :type $plugin: Plugin
        :param $plugin: Record of plugin to register.

    .. php:method:: isRegistered(Plugin $plugin)

        Return whether a plugin is registered or not.

        :type $plugin: Plugin
        :param $plugin:
        :returns: bool Whether the plugin is registered or not.

    .. php:method:: load(Plugin $plugin, $force = false, $pluginsWaitingToLoad = array())

        Load a plugin (and make sure the plugin API is available).

        To be loaded, the plugin must be installed, active, and not have a newer
        version. If loaded, the plugin will attempt to first load all plugins,
        both required and optional, that the plugin uses.  However, it will not
        load a plugin that it uses if that plugin is not installed and activated.

        :type $plugin: Plugin
        :param $plugin:
        :type $force: bool
        :param $force: If true, throws exceptions if a plugin can't be loaded.
        :type $pluginsWaitingToLoad: array
        :param $pluginsWaitingToLoad: Plugins waiting to be loaded

    .. php:method:: _canLoad($plugin, $force)

        Determine whether or not a plugin can be loaded.  To be loaded, it must
        meet the following criteria:
        - Has a plugin.php file.
        - Is installed.
        - Is active.
        - Meets the minimum required version of Omeka (in plugin.ini).
        - Is not already loaded.
        - Does not have a new version available.

        :type $plugin: Plugin
        :param $plugin: Plugin to test.
        :type $force: bool
        :param $force: If true, throw an exception if the plugin can't be loaded.
        :returns: bool

    .. php:method:: hasPluginBootstrap($pluginDirName)

        Check whether a plugin has a bootstrap file.

        :type $pluginDirName: string|Plugin
        :param $pluginDirName:
        :returns: bool

    .. php:method:: getPluginClassName($pluginDirName)

        Return the valid plugin class name.

        :type $pluginDirName: string
        :param $pluginDirName:
        :returns: string

    .. php:method:: getPluginFilePath($pluginDirName)

        Return the path to the plugin.php file.

        :type $pluginDirName: string
        :param $pluginDirName:
        :returns: string

    .. php:method:: getPluginClassFilePath($pluginDirName)

        Return the path to the plugin class file.

        :type $pluginDirName: string
        :param $pluginDirName:
        :returns: string

    .. php:method:: getPlugins()

        Return a list of all the plugins that have been loaded (or attempted to
        be loaded) thus far.

        :returns: array List of Plugin objects.

    .. php:method:: getPlugin($directoryName)

        Get a plugin object by name (plugin subdirectory name).

        :type $directoryName: string
        :param $directoryName: Plugin name.
        :returns: Plugin|null

    .. php:method:: _loadPluginBootstrap(Plugin $plugin)

        Loads the plugin bootstrap file for a plugin.

        :type $plugin: Plugin
        :param $plugin:
