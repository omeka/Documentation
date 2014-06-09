------
Plugin
------

.. php:class:: Plugin

    Package: :doc:`Record </Reference/packages/Record/index>`

    A plugin and its metadata.
    
    This record represents the data Omeka stores about each plugin and uses tomanage the plugins, it is not a part of any plugin itself.

    .. php:attr:: name
    
        Directory name for the plugin.

    .. php:attr:: active
    
        Whether this plugin is active.

    .. php:attr:: version
    
        Version string for the currently-installed plugin.

    .. php:attr:: _displayName
    
        Human-readable display name of the plugin.

    .. php:attr:: _author
    
        The plugin's author.

    .. php:attr:: _description
    
        Description of the plugin.

    .. php:attr:: _link
    
        URL for documentation or further information about the plugin.

    .. php:attr:: _loaded
    
        Whether the plugin has been loaded.

    .. php:attr:: _hasConfig
    
        Whether the plugin has a custom configuration form.

    .. php:attr:: _requiredPlugins
    
        Directory names of required plugins.

    .. php:attr:: _optionalPlugins
    
        Directory names of optional plugins.

    .. php:attr:: _minimumOmekaVersion
    
        Minimum Omeka version requirement for the plugin.

    .. php:attr:: _testedUpToVersion
    
        Maximum version of Omeka that the plugin has been tested on.

    .. php:attr:: _iniVersion
    
        Version of the plugin that is stored in the INI.

    .. php:attr:: _iniTags
    
        List of tags associated with this plugin, as retrieved from
        the ini file.

    .. php:method:: _validate()
    
        Validate the plugin.
        
        The directory name must be set.

    .. php:method:: getDirectoryName()
    
        Get the name of the directory containing the plugin.
        
        :returns: string

    .. php:method:: setDirectoryName(string $name)
    
        Set the name of the directory containing the plugin.
        
        :param string $name: 
        :returns: Plugin

    .. php:method:: getDisplayName()
    
        Get the human-readable name of the plugin.
        
        If there is no human-readable name available, returns the directory nameinstead.
        
        :returns: string

    .. php:method:: setDisplayName(string $name)
    
        Set the human-readable name of the plugin.
        
        :param string $name: 
        :returns: Plugin

    .. php:method:: getAuthor()
    
        Get the plugin's author.
        
        :returns: string

    .. php:method:: setAuthor(string $author)
    
        Set the author's name.
        
        :param string $author: 
        :returns: Plugin

    .. php:method:: getDescription()
    
        Get the description of the plugin.
        
        :returns: string

    .. php:method:: setDescription(string $description)
    
        Set the description of the plugin.
        
        :param string $description: 
        :returns: Plugin

    .. php:method:: getMinimumOmekaVersion()
    
        Get the minimum version of Omeka that this plugin requires to work.
        
        :returns: string

    .. php:method:: setMinimumOmekaVersion(string $version)
    
        Set the minimum required version of Omeka.
        
        :param string $version: 
        :returns: Plugin

    .. php:method:: getTestedUpToOmekaVersion()
    
        Get the version of Omeka that this plugin is tested up to.
        
        :returns: string

    .. php:method:: setTestedUpToOmekaVersion(string $version)
    
        Set the version of Omeka that this plugin is tested up to.
        
        :param string $version: 
        :returns: Plugin

    .. php:method:: getRequiredPlugins()
    
        Get the list of plugins that are required for this plugin to work.
        
        :returns: array

    .. php:method:: setRequiredPlugins($plugins)
    
        Set the list of plugins that are required for this plugin to work.
        
        :param unknown $plugins: 
        :returns: Plugin

    .. php:method:: getOptionalPlugins()
    
        Get the list of plugins that can be used, but are not required by, this
        plugin.
        
        :returns: array

    .. php:method:: setOptionalPlugins($plugins)
    
        Set the list of optional plugins.
        
        :param unknown $plugins: 
        :returns: Plugin

    .. php:method:: getIniTags()
    
        Get the list of tags for this plugin (from the ini file).
        
        :returns: array

    .. php:method:: setIniTags($tags)
    
        Set the list of tags for this plugin.
        
        :param unknown $tags: 
        :returns: Plugin

    .. php:method:: getSupportLinkUrl()
    
        Get the support link url from plugin.ini
        
        :returns: string

    .. php:method:: setSupportLinkUrl($link)
    
        Set the support link url from plugin.ini
        
        :param unknown $link: 
        :returns: Plugin

    .. php:method:: getLinkUrl()
    
        Get the URL link from the plugin.ini.
        
        :returns: string

    .. php:method:: setLinkUrl(string $link)
    
        Set the link from the plugin.ini.
        
        :param string $link: 
        :returns: Plugin

    .. php:method:: isInstalled()
    
        Determine whether the Plugin has been installed.
        
        :returns: bool

    .. php:method:: isLoaded()
    
        Determine whether the Plugin has been loaded.
        
        :returns: bool

    .. php:method:: setLoaded(bool $flag)
    
        Set whether the plugin has been loaded.
        
        :param bool $flag: 
        :returns: Plugin

    .. php:method:: isActive()
    
        Determine whether the plugin is active.
        
        :returns: bool

    .. php:method:: setActive(bool $flag)
    
        Set whether the plugin is active.
        
        :param bool $flag: 
        :returns: Plugin

    .. php:method:: hasConfig()
    
        Determine whether the plugin has a custom configuration form.
        
        :returns: bool

    .. php:method:: setHasConfig(bool $flag)
    
        Set whether the plugin has a custom configuration form.
        
        :param bool $flag: 
        :returns: Plugin

    .. php:method:: getIniVersion()
    
        Get the version of the plugin stored in the INI file.
        
        :returns: string

    .. php:method:: setIniVersion(string $version)
    
        Set the version of the plugin that is indicated by the INI file.
        
        :param string $version: 
        :returns: Plugin

    .. php:method:: getDbVersion()
    
        Get the version of the plugin that is stored in the database.
        
        :returns: string

    .. php:method:: setDbVersion(string $version)
    
        Set the version of the plugin that is stored in the database.
        
        :param string $version: 
        :returns: Plugin

    .. php:method:: hasNewVersion()
    
        Determine whether there is a new version of the plugin available.
        
        :returns: bool

    .. php:method:: meetsOmekaMinimumVersion()
    
        Determine whether this Omeka install meets the plugin's minimum version
        requirements.
        
        If the field is not set, assume that it meets the requirements.  If thefield is set, it must be greater than the current version of Omeka.
        
        :returns: bool

    .. php:method:: meetsOmekaTestedUpToVersion()
    
        Determine whether this Omeka version has been tested for use with the
        plugin.
        
        :returns: bool

    .. php:method:: getResourceId()
    
        Declare the Plugin model as relating to the Plugins ACL resource.
        
        :returns: string