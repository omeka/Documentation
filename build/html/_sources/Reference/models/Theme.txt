-----
Theme
-----

.. php:class:: Theme

    Dummy model to simulate the other ActiveRecord models

    .. php:attr:: path
    


    .. php:attr:: directory
    


    .. php:attr:: image
    


    .. php:attr:: author
    


    .. php:attr:: title
    


    .. php:attr:: description
    


    .. php:attr:: license
    


    .. php:attr:: website
    


    .. php:attr:: omeka_minimum_version
    


    .. php:method:: __construct($themeName)
    
        :param unknown $themeName:

    .. php:method:: setDirectoryName($dir)
    
        :param unknown $dir:

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

    .. php:method:: setImage($fileName)
    
        :param unknown $fileName:

    .. php:method:: setIni($fileName)
    
        :param unknown $fileName:

    .. php:method:: setConfig($fileName)
    
        :param unknown $fileName:

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
        :returns: void

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
        :returns: void

    .. php:method:: getOptionName(string $themeName)
    
        Get the name of a specific theme's option.  Each theme has a single option in the option's table, 
        which stores all of the configuration options for that theme
        
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

