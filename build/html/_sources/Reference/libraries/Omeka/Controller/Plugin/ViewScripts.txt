-----------------------------------
Omeka_Controller_Plugin_ViewScripts
-----------------------------------

.. php:class:: Omeka_Controller_Plugin_ViewScripts

    Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

    Sets up view script search paths on a per-request basis.

    .. php:attr:: _view
    
        Registered view object.

    .. php:attr:: _dbOptions
    
        List of options from the database.

    .. php:attr:: _baseThemePath
    
        Base path to themes directory.

    .. php:attr:: _webBaseThemePath
    
        Base web-accesible path to themes.

    .. php:attr:: _pluginMvc
    
        MVC plugin behaviors class.

    .. php:method:: __construct(array $options, Omeka_Plugin_Mvc $pluginMvc)
    
        :param array $options: List of options.
        :param Omeka_Plugin_Mvc $pluginMvc: Plugin MVC class.

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)
    
        Add the appropriate view scripts directories for a given request.
        This is pretty much the glue between the plugin broker and the
        View object, since it uses data from the plugin broker to determine what
        script paths will be available to the view.
        
        :param Zend_Controller_Request_Abstract $request: Request object.
        :returns: void

    .. php:method:: _setupPathsForPlugin(string $pluginModuleName, string $themeType)
    
        Set up the asset paths for a plugin.
        
        If you're in a plugin, check in this order:
        1. plugin view scripts (only for that plugin)
        2. plugin view scripts for other plugins
        3. theme view scripts
        
        This means that it needs to add the paths in the reverse order of what needsto be checked first, so theme paths first and then plugin paths.
        
        :param string $pluginModuleName: The module name for the plugin.
        :param string $themeType: The type of theme: 'admin' or 'public'.
        :returns: void

    .. php:method:: _setupPathsForTheme(string $themeType)
    
        Set up the asset paths for the theme.
        
        If you're in one of the themes, check in this order:1. theme view scripts2. all plugin view scripts
        
        :param string $themeType: The type of theme: 'admin' or 'public'.
        :returns: void

    .. php:method:: _addPluginPaths(string $themeType, string $pluginModuleName)
    
        Add asset paths for a plugin.
        
        :param string $themeType: The type of theme: 'admin' or 'public'.
        :param string $pluginModuleName: The module name for the plugin.
        :returns: void

    .. php:method:: _addPathToView(string $scriptPath)
    
        Add a new script path for a plugin to the view.
        
        :param string $scriptPath: Path from plugins dir to script dir.
        :returns: void

    .. php:method:: _getView()
    
        Gets the view from the registry.
        
        The initial call to the registry caches the view in this class.
        
        :returns: Zend_View

    .. php:method:: _addSharedViewsDir()
    
        Add the global views from the view scripts directory to the view.
        
        :returns: void

    .. php:method:: _addThemePaths(string $theme)
    
        Add script and asset paths for a theme to the view.
        
        :param string $theme: Theme type; either 'public' or 'admin'.
        :returns: void

    .. php:method:: _addOverridePathForPlugin(string $theme, string $pluginModuleName)
    
        Add theme view path for override views for a given plugin.
        
        :param string $theme: Theme type; 'public' or 'admin'
        :param string $pluginModuleName:

    .. php:method:: getThemeOption(string $type)
    
        Retrieve the option from the database that contains the directory of
        the theme to render.
        
        :param string $type: Currently either 'admin' or 'public'.
        :returns: string