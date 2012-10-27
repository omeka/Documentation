----------------
Omeka_Plugin_Mvc
----------------

.. php:class:: Omeka_Plugin_Mvc

    Package: :doc:`Plugin </Reference/packages/Plugin/index>`

    Connects plugins with Omeka's model-view-controller system.

    .. php:attr:: _basePath
    
        Path to the root plugins directory.

    .. php:attr:: _pluginViewDirs
    
        View script directories that have been added by plugins.

    .. php:method:: __construct(string $basePath)
    
        :param string $basePath: Plugins directory path.

    .. php:method:: addThemeDir(string $pluginDirName, string $path, string $themeType, string $moduleName)
    
        Add a theme directory to the list of plugin-added view directories.
        
        Used by the add_theme_pages() helper to create a list of directories thatcan store static pages that integrate into
        the themes.
        
        :param string $pluginDirName: Plugin name.
        :param string $path: Path to directory to add.
        :param string $themeType: Type of theme ('public', 'admin', or 'shared').
        :param string $moduleName: MVC module name.
        :returns: void

    .. php:method:: getModuleViewScriptDirs(string $moduleName)
    
        Retrieve the list of plugin-added view script directories.
        
        :param string $moduleName: (optional) MVC module name.
        :returns: array List of indexed directory names.

    .. php:method:: addControllerDir(string $pluginDirName, string $moduleName)
    
        Make an entire directory of controllers available to the front
        controller.
        
        This has to use addControllerDirectory() instead of addModuleDirectory()because module names are case-sensitive and
        module directories need to belowercased to conform to Zend's weird naming conventions.
        
        :param string $pluginDirName: Plugin name.
        :param string $moduleName: MVC module name.
        :returns: void

    .. php:method:: addApplicationDirs(string $pluginDirName)
    
        Set up the following directory structure for plugins:
        
        controllers/models/libraries/views/admin/public/shared/
        
        This also adds these folders to the correct include paths.
        
        :param string $pluginDirName: Plugin name.
        :returns: void

    .. php:method:: _getModuleName(string $pluginDirName)
    
        Retrieve the module name for the plugin (based on the directory name
        of the plugin).
        
        :param string $pluginDirName: Plugin name.
        :returns: string Plugin MVC module name.

    .. php:method:: _hasIncludePath(string $path)
    
        Check include path to see if it already contains a specific path.
        
        :param string $path: 
        :returns: boolean