-----------------------------------
Omeka_Controller_Plugin_ViewScripts
-----------------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_ViewScripts

extends :php:class:`Zend_Controller_Plugin_Abstract`

    Sets up view script search paths on a per-request basis.

    .. php:attr:: _view

        protected Zend_View

        Registered view object.

    .. php:attr:: _dbOptions

        protected array

        List of options from the database.

    .. php:attr:: _baseThemePath

        protected string

        Base path to themes directory.

    .. php:attr:: _webBaseThemePath

        protected string

        Base web-accesible path to themes.

    .. php:attr:: _pluginMvc

        protected Omeka_Plugin_Mvc

        MVC plugin behaviors class.

    .. php:method:: __construct($options, Omeka_Plugin_Mvc $pluginMvc)

        :type $options: array
        :param $options: List of options.
        :type $pluginMvc: Omeka_Plugin_Mvc
        :param $pluginMvc: Plugin MVC class.

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)

        Add the appropriate view scripts directories for a given request.
        This is pretty much the glue between the plugin broker and the
        View object, since it uses data from the plugin broker to determine what
        script paths will be available to the view.

        :type $request: Zend_Controller_Request_Abstract
        :param $request: Request object.
        :returns: void

    .. php:method:: _addPathsToView($paths)

        Add multiple script paths.

        :type $paths: array
        :param $paths: The paths to add.

    .. php:method:: _addPathToView($scriptPath)

        Add a new script path for a plugin to the view.

        :type $scriptPath: string
        :param $scriptPath: Path from plugins dir to script dir.
        :returns: void

    .. php:method:: _getView()

        Gets the view from the registry.

        The initial call to the registry caches the view in this class.

        :returns: Zend_View

    .. php:method:: _addSharedViewsDir()

        Add the global views from the view scripts directory to the view.

        :returns: void

    .. php:method:: _addThemePaths($theme)

        Add script and asset paths for a theme to the view.

        :type $theme: string
        :param $theme: Theme type; either 'public' or 'admin'.
        :returns: void

    .. php:method:: _addOverridePathForPlugin($theme, $pluginModuleName)

        Add theme view path for override views for a given plugin.

        :type $theme: string
        :param $theme: Theme type; 'public' or 'admin'
        :type $pluginModuleName: string
        :param $pluginModuleName:

    .. php:method:: getThemeOption($type)

        Retrieve the option from the database that contains the directory of
        the theme to render.

        :type $type: string
        :param $type: Currently either 'admin' or 'public'.
        :returns: string
