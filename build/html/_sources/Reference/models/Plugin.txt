------
Plugin
------

.. php:class:: Plugin

    Package: :doc:`/Reference/packages/Record/index`

    A plugin and its metadata.

    .. php:attr:: name
    


    .. php:attr:: active
    


    .. php:attr:: version
    


    .. php:attr:: _displayName
    


    .. php:attr:: _author
    


    .. php:attr:: _description
    


    .. php:attr:: _link
    


    .. php:attr:: _loaded
    


    .. php:attr:: _hasConfig
    


    .. php:attr:: _requiredPlugins
    


    .. php:attr:: _optionalPlugins
    


    .. php:attr:: _minimumOmekaVersion
    


    .. php:attr:: _testedUpToVersion
    


    .. php:attr:: _iniVersion
    


    .. php:attr:: _iniTags
    


    .. php:method:: _validate()

    .. php:method:: getDirectoryName()
    
        Get the name of the directory containing the plugin.

    .. php:method:: setDirectoryName(string $name)
    
        Set the name of the directory containing the plugin.
        
        :param string $name:

    .. php:method:: getDisplayName()
    
        Get the human-readable name of the plugin, e.g. "Dublin Core Extended".
        
        If there is no human-readable name available, returns the directory name instead.

    .. php:method:: setDisplayName(string $name)
    
        Set the human-readable name of the plugin.
        
        :param string $name:

    .. php:method:: getAuthor()
    
        Get the author's name.

    .. php:method:: setAuthor(string $author)
    
        Set the author's name.
        
        :param string $author:

    .. php:method:: getDescription()
    
        Get the description of the plugin.

    .. php:method:: setDescription(string $description)
    
        Set the description of the plugin.
        
        :param string $description:

    .. php:method:: getMinimumOmekaVersion()
    
        Get the minimum version of Omeka that this plugin requires to work.

    .. php:method:: setMinimumOmekaVersion(string $version)
    
        Set the minimum required version of Omeka.
        
        :param string $version:

    .. php:method:: getTestedUpToOmekaVersion()
    
        Get the version of Omeka that this plugin is tested up to.

    .. php:method:: setTestedUpToOmekaVersion(string $version)
    
        Set the version of Omeka that this plugin is tested up to.
        
        :param string $version:

    .. php:method:: getRequiredPlugins()
    
        Get the list of plugins that are required for this plugin to work.

    .. php:method:: setRequiredPlugins($plugins)
    
        Set the list of plugins that are required for this plugin to work.
        
        :param unknown $plugins:

    .. php:method:: getOptionalPlugins()
    
        Get the list of plugins that can be used, but are not required by, this
        plugin.

    .. php:method:: setOptionalPlugins($plugins)
    
        Set the list of optional plugins.
        
        :param unknown $plugins:

    .. php:method:: getIniTags()
    
        Get the list of tags for this plugin (from the ini file).

    .. php:method:: setIniTags($tags)
    
        Set the list of tags for this plugin.
        
        :param unknown $tags:

    .. php:method:: getLinkUrl()
    
        Get the URL link from the plugin.ini.

    .. php:method:: setLinkUrl(string $link)
    
        Set the link from the plugin.ini.
        
        :param string $link:

    .. php:method:: isInstalled()
    
        Whether or not the Plugin has been installed.
        
        :returns: boolean

    .. php:method:: isLoaded()
    
        :returns: boolean

    .. php:method:: setLoaded(boolean $flag)
    
        :param boolean $flag:

    .. php:method:: isActive()
    
        Whether or not the plugin has been activated through the UI.

    .. php:method:: setActive($flag)
    
        Set whether or not the plugin has been activated.
        
        :param unknown $flag:

    .. php:method:: hasConfig()
    
        Whether or not the plugin has a custom configuration hook.

    .. php:method:: setHasConfig(boolean $flag)
    
        Set whether or not the plugin has a custom configuration hook.
        
        :param boolean $flag:

    .. php:method:: getIniVersion()
    
        Get the version of the plugin stored in the ini file.

    .. php:method:: setIniVersion(string $version)
    
        Set the version of the plugin that is indicated by the ini file.
        
        :param string $version:

    .. php:method:: getDbVersion()
    
        Get the version of the plugin that is stored in the database.

    .. php:method:: setDbVersion(string $version)
    
        Set the version of the plugin that is stored in the database.
        
        :param string $version:

    .. php:method:: hasNewVersion()
    
        Determine whether or not there is a new version of the plugin available.

    .. php:method:: meetsOmekaMinimumVersion()
    
        Determine whether the plugin meets the minimum version requirements for Omeka.
        
        If the field is not set, assume that it meets the requirements.  If the field is set, it must be greater than the
        current version of Omeka.

    .. php:method:: meetsOmekaTestedUpToVersion()

    .. php:method:: getResourceId()