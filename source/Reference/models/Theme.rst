-----
Theme
-----

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Theme

    A theme and its metadata.

    Unlike most other models, Themes are not stored in the database. This model relies only on INI data, but acts like an Omeka_Record_AbstractRecord model.

    .. php:const:: THEME_IMAGE_FILE_NAME

        Filename for the theme screenshot.

    .. php:const:: THEME_INI_FILE_NAME

        Filename for the theme INI file.

    .. php:const:: THEME_CONFIG_FILE_NAME

        Filename for the theme config form INI file.

    .. php:const:: PUBLIC_THEME_OPTION

        Option name for the current public theme.

    .. php:const:: ADMIN_THEME_OPTION

        Option name for the current admin theme.

    .. php:attr:: path

        string

        Absolute path to the theme.

    .. php:attr:: directory

        string

        Directory name of the theme.

    .. php:attr:: image

        string

        Web path to the theme screenshot.

    .. php:attr:: author

        string

        The theme's author.

    .. php:attr:: title

        string

        The theme's title.

    .. php:attr:: description

        string

        The theme's description.

    .. php:attr:: license

        string

        The software license for the theme.

    .. php:attr:: website

        string

        A link to the theme's website.

    .. php:attr:: omeka_minimum_version

        string

        The minimum Omeka version the theme will run on.

    .. php:method:: __construct($themeName)

        Set the INI and file data for the theme, given its directory name.

        :type $themeName: string
        :param $themeName: Directory name.

    .. php:method:: setDirectoryName($dir)

        Set the theme's directory name and path.

        :type $dir: string
        :param $dir: Directory name.

    .. php:method:: getScriptPath()

        Get the physical path to the theme's scripts.

        :returns: string Physical path.

    .. php:method:: getAssetPath()

        Get the web path to the theme's assets.

        :returns: string Web path.

    .. php:method:: getScriptPathForPlugin($pluginModuleName)

        Get the physical path to the theme's override scripts for the given
        plugin.

        :type $pluginModuleName: string
        :param $pluginModuleName: (i.e., 'exhibit-builder')
        :returns: string Physical path.

    .. php:method:: getAssetPathForPlugin($pluginModuleName)

        Get the web path to the theme's override assets for the given plugin.

        :type $pluginModuleName: string
        :param $pluginModuleName: (i.e., 'exhibit-builder')
        :returns: string Web path.

    .. php:method:: setImage($fileName)

        Set the web path to the screenshot, if it exists.

        :type $fileName: string
        :param $fileName: Relative filename of the image to check.

    .. php:method:: setIni($fileName)

        Load data from the INI file at the given path.

        :type $fileName: string
        :param $fileName: Relative filename of the INI file.

    .. php:method:: setConfig($fileName)

        Check for a theme config file at the given location.

        :type $fileName: string
        :param $fileName: Relative filename of the theme config.ini.

    .. php:method:: getCurrentThemeName($type = null)

        Get the directory name of the current theme.

        :type $type: string
        :param $type: 'admin' or 'public', defaults to current type
        :returns: string

    .. php:method:: getAllThemes()

        Retrieve all themes

        :returns: array An array of theme objects

    .. php:method:: getAllAdminThemes()

        Retrieve all admin themes

        :returns: array An array of theme objects

    .. php:method:: getTheme($themeName)

        Retrieve a theme.

        :type $themeName: string
        :param $themeName: The name of the theme.
        :returns: Theme A theme object

    .. php:method:: setOptions($themeName, $themeConfigOptions)

        Set theme configuration options.

        :type $themeName: string
        :param $themeName: The name of the theme
        :type $themeConfigOptions: array
        :param $themeConfigOptions: An associative array of configuration options, where each key is a configuration form input name and each value is a string value of that configuration form input

    .. php:method:: getOptions($themeName)

        Get theme configuration options.

        :type $themeName: string
        :param $themeName: The name of the theme
        :returns: array An associative array of configuration options, where each key is a configuration form input name and each value is a string value of that configuration form input

    .. php:method:: getOption($themeName, $themeOptionName)

        Get the value of a theme configuration option.

        :type $themeName: string
        :param $themeName: The name of the theme
        :type $themeOptionName: string
        :param $themeOptionName: The name of the theme option
        :returns: string The value of the theme option

    .. php:method:: setOption($themeName, $themeOptionName, $themeOptionValue)

        Set the value of a theme configuration option.

        :type $themeName: string
        :param $themeName: The name of the theme
        :type $themeOptionName: string
        :param $themeOptionName: The name of the theme option
        :param $themeOptionValue:

    .. php:method:: getOptionName($themeName)

        Get the name of a specific theme's option.  Each theme has a single
        option in the option's table, which stores all of the configuration
        options for that theme

        :type $themeName: string
        :param $themeName: The name of the theme
        :returns: string The name of a specific theme's option.

    .. php:method:: getUploadedFileName($themeName, $optionName, $fileName)

        Get the name of a file uploaded as a theme configuration option.
        This is the name of the file after it has been uploaded and renamed.

        :type $themeName: string
        :param $themeName: The name of the theme
        :type $optionName: string
        :param $optionName: The name of the theme option associated with the uploaded file
        :type $fileName: string
        :param $fileName: The name of the uploaded file
        :returns: string The name of an uploaded file for the theme.

    .. php:method:: _parseWebsite($website)

        Parses the website string to confirm whether it has a scheme.

        :type $website: string
        :param $website: The website given in the theme's INI file.
        :returns: string The website URL with a prepended scheme.
