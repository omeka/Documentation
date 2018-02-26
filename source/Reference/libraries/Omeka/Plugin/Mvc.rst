----------------
Omeka_Plugin_Mvc
----------------

Package: :doc:`Plugin </Reference/packages/Plugin/index>`

.. php:class:: Omeka_Plugin_Mvc

    Connects plugins with Omeka's model-view-controller system.

    .. php:attr:: _basePath

        protected string

        Path to the root plugins directory.

    .. php:attr:: _pluginViewDirs

        protected array

        View script directories that have been added by plugins.

    .. php:attr:: _pluginHelpersDirs

        protected array

        View helper directories from plugins.

    .. php:method:: __construct($basePath)

        :type $basePath: string
        :param $basePath: Plugins directory path.

    .. php:method:: addThemeDir($pluginDirName, $path, $themeType, $moduleName)

        Add a theme directory to the list of plugin-added view directories.

        Used by the add_theme_pages() helper to create a list of directories that
        can store static pages that integrate into the themes.

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :type $path: string
        :param $path: Path to directory to add.
        :type $themeType: string
        :param $themeType: Type of theme ('public', 'admin', or 'shared').
        :type $moduleName: string
        :param $moduleName: MVC module name.

    .. php:method:: getViewScriptDirs($themeType)

        Retrieve the list of plugin-added view script directories.

        :type $themeType: string
        :param $themeType: Type of theme (public or admin)
        :returns: array Module-name-indexed directory names.

    .. php:method:: getHelpersDirs()

        Get all the existing plugin view helper dirs, indexed by plugin name.

        :returns: array

    .. php:method:: addControllerDir($pluginDirName, $moduleName)

        Make an entire directory of controllers available to the front
        controller.

        This has to use addControllerDirectory() instead of addModuleDirectory()
        because module names are case-sensitive and module directories need to be
        lowercased to conform to Zend's weird naming conventions.

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :type $moduleName: string
        :param $moduleName: MVC module name.

    .. php:method:: addApplicationDirs($pluginDirName)

        Set up the following directory structure for plugins:

        controllers/
        models/
        libraries/
        views/
        admin/
        public/
        shared/

        This also adds these folders to the correct include paths.

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.

    .. php:method:: _getModuleName($pluginDirName)

        Retrieve the module name for the plugin (based on the directory name
        of the plugin).

        :type $pluginDirName: string
        :param $pluginDirName: Plugin name.
        :returns: string Plugin MVC module name.

    .. php:method:: _hasIncludePath($path)

        Check include path to see if it already contains a specific path.

        :type $path: string
        :param $path:
        :returns: bool
