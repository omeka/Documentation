-----
Theme
-----

.. php:class:: Theme

    Package: :doc:`Record </Reference/packages/Record/index>`

    A theme and its metadata.
    
    Unlike most other models, Themes are not stored in the database. This modelrelies only on INI data, but acts like an Omeka_Record_AbstractRecord model.

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
    
        Absolute path to the theme.

    .. php:attr:: directory
    
        Directory name of the theme.

    .. php:attr:: image
    
        Web path to the theme screenshot.

    .. php:attr:: author
    
        The theme's author.

    .. php:attr:: title
    
        The theme's title.

    .. php:attr:: description
    
        The theme's description.

    .. php:attr:: license
    
        The software license for the theme.

    .. php:attr:: website
    
        A link to the theme's website.

    .. php:attr:: omeka_minimum_version
    
        The minimum Omeka version the theme will run on.

    .. php:method:: __construct(string $themeName)
    
        Set the INI and file data for the theme, given its directory name.
        
        :param string $themeName: Directory name.

    .. php:method:: setDirectoryName(string $dir)
    
        Set the theme's directory name and path.
        
        :param string $dir: Directory name.

    .. php:method:: getScriptPath()
    
        Get the physical path to the theme's scripts.
        
        :returns: string Physical path.

    .. php:method:: getAssetPath()
    
        Get the web path to the theme's assets.
        
        :returns: string Web path.

    .. php:method:: getScriptPathForPlugin(string $pluginModuleName)
    
        Get the physical path to the theme's override scripts for the given plugin.
        
        :param string $pluginModuleName: (i.e., 'exhibit-builder')
        :returns: string Physical path.

    .. php:method:: getAssetPathForPlugin(string $pluginModuleName)
    
        Get the web path to the theme's override assets for the given plugin.
        
        :param string $pluginModuleName: (i.e., 'exhibit-builder')
        :returns: string Web path.

    .. php:method:: setImage(string $fileName)
    
        Set the web path to the screenshot, if it exists.
        
        :param string $fileName: Relative filename of the image to check.

    .. php:method:: setIni(string $fileName)
    
        Load data from the INI file at the given path.
        
        :param string $fileName: Relative filename of the INI file.

    .. php:method:: setConfig(string $fileName)
    
        Check for a theme config file at the given location.
        
        :param string $fileName: Relative filename of the theme config.ini.

    .. php:method:: getCurrentThemeName(string $type)
    
        Get the directory name of the current theme.
        
        :param string $type: 'admin' or 'public', defaults to current type
        :returns: string

    .. php:method:: getAllThemes()
    
        Retrieve all themes
        
        :returns: array An array of theme objects

    .. php:method:: getTheme(string $themeName)
    
        Retrieve a theme.
        
        :param string $themeName:  The name of the theme.
        :returns: Theme A theme object

    .. php:method:: setOptions(string $themeName, array $themeConfigOptions)
    
        Set theme configuration options.
        
        :param string $themeName:  The name of the theme
        :param array $themeConfigOptions: An associative array of configuration options, where each key is a configuration form input name and each value is a string value of that configuration form input

    .. php:method:: getOptions(string $themeName)
    
        Get theme configuration options.
        
        :param string $themeName:  The name of the theme
        :returns: array An associative array of configuration options, where each key is a configuration form input name and each value is a string value of that configuration form input

    .. php:method:: getOption(string $themeName, string $themeOptionName)
    
        Get the value of a theme configuration option.
        
        :param string $themeName:  The name of the theme
        :param string $themeOptionName: The name of the theme option
        :returns: string The value of the theme option

    .. php:method:: setOption(string $themeName, string $themeOptionName, $themeOptionValue)
    
        Set the value of a theme configuration option.
        
        :param string $themeName:  The name of the theme
        :param string $themeOptionName: The name of the theme option
        :param unknown $themeOptionValue:

    .. php:method:: getOptionName(string $themeName)
    
        Get the name of a specific theme's option.  Each theme has a single
        option in the option's table, which stores all of the configuration
        options for that theme
        
        :param string $themeName:  The name of the theme
        :returns: string The name of a specific theme's option.

    .. php:method:: getUploadedFileName(string $themeName, string $optionName, string $fileName)
    
        Get the name of a file uploaded as a theme configuration option.  
        This is the name of the file after it has been uploaded and renamed.
        
        :param string $themeName:  The name of the theme
        :param string $optionName: The name of the theme option associated with the uploaded file
        :param string $fileName: The name of the uploaded file
        :returns: string The name of an uploaded file for the theme.

    .. php:method:: _parseWebsite(string $website)
    
        Parses the website string to confirm whether it has a scheme.
        
        :param string $website: The website given in the theme's INI file.
        :returns: string The website URL with a prepended scheme.