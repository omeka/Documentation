-------------------
Omeka_Plugin_Loader
-------------------

.. php:class:: Omeka_Plugin_Loader

    Package: :doc:`/Reference/packages/Plugin\Loader/index`

    Loads plugins for any given request.
    
    This will iterate through the plugins root directory and load all plugin.phpfiles by require()'ing them.

    .. php:attr:: _broker
    
        Plugin broker object.

    .. php:attr:: _iniReader
    
        Plugin INI reader object.

    .. php:attr:: _mvc
    
        Plugin MVC object.

    .. php:attr:: _basePath
    
        Plugins directory.

    .. php:attr:: _plugins
    
        An array of all plugins (installed or not) that are currently located
        in the plugins/ directory.

    .. php:method:: __construct(Omeka_Plugin_Broker $broker, Omeka_Plugin_Ini $iniReader, Omeka_Plugin_Mvc $mvc, string $pluginsBaseDir)
    
        :param Omeka_Plugin_Broker $broker: Plugin broker.
        :param Omeka_Plugin_Ini $iniReader: plugin.ini reader.
        :param Omeka_Plugin_Mvc $mvc: Plugin MVC object.
        :param string $pluginsBaseDir: Plugins directory.

    .. php:method:: loadPlugins(array $plugins, boolean $force = )
    
        Load a list of plugins.
        
        :param array $plugins: List of Plugin records to load.
        :param boolean $force: If true, throws exceptions for plugins that cannot be loaded for some reason.
        :returns: void

    .. php:method:: registerPlugin(Plugin $plugin)
    
        Register a plugin so that it can be accessed by other plugins (if necessary)
        during the load process.
        
        There should only be a single instance of a plugin per directory name.Registering a plugin more than once, i.e.
        loading a plugin again after thefirst time failed, will not cause a problem as long as the same instancewas
        registered.
        
        :param Plugin $plugin: Record of plugin to register.
        :returns: void

    .. php:method:: isRegistered(Plugin $plugin)
    
        Return whether a plugin is registered or not.
        
        :param Plugin $plugin: 
        :returns: boolean Whether the plugin is registered or not.

    .. php:method:: load(Plugin $plugin, boolean $force = , array $pluginsWaitingToLoad = Array)
    
        Load a plugin (and make sure the plugin API is available).
        
        To be loaded, the plugin must be installed, active, and not have a newerversion. If loaded, the plugin will attempt
        to first load all plugins,both required and optional, that the plugin uses.  However, it will notload a plugin that
        it uses if that plugin is not installed and activated.
        
        :param Plugin $plugin: 
        :param boolean $force: If true, throws exceptions if a plugin can't be loaded.
        :param array $pluginsWaitingToLoad: Plugins waiting to be loaded
        :returns: void

    .. php:method:: _canLoad(Plugin $plugin, boolean $force)
    
        Determine whether or not a plugin can be loaded.  To be loaded, it must
        meet the following criteria:
        - Has a plugin.php file.
        - Is installed.
        - Is active.
        - Meets the minimum required version of Omeka (in plugin.ini).
        - Is not already loaded.
        - Does not have a new version available.
        
        :param Plugin $plugin: Plugin to test.
        :param boolean $force: If true, throw an exception if the plugin can't be loaded.
        :returns: boolean

    .. php:method:: hasPluginBootstrap(string|Plugin $pluginDirName)
    
        Check whether a plugin has a bootstrap file.
        
        :param string|Plugin $pluginDirName: 
        :returns: boolean

    .. php:method:: getPluginClassName(string $pluginDirName)
    
        Return the valid plugin class name.
        
        :param string $pluginDirName: 
        :returns: string

    .. php:method:: getPluginFilePath(string $pluginDirName)
    
        Return the path to the plugin.php file.
        
        :param string $pluginDirName: 
        :returns: string

    .. php:method:: getPluginClassFilePath(string $pluginDirName)
    
        Return the path to the plugin class file.
        
        :param string $pluginDirName: 
        :returns: string

    .. php:method:: getPlugins()
    
        Return a list of all the plugins that have been loaded (or attempted to
        be loaded) thus far.
        
        :returns: array List of Plugin objects.

    .. php:method:: getPlugin(string $directoryName)
    
        Get a plugin object by name (plugin subdirectory name).
        
        :param string $directoryName: Plugin name.
        :returns: Plugin|null

    .. php:method:: _loadPluginBootstrap(Plugin $plugin)
    
        Loads the plugin bootstrap file for a plugin.
        
        :param Plugin $plugin: 
        :returns: void