------
Plugin
------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Plugin

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    A plugin and its metadata.

    This record represents the data Omeka stores about each plugin and uses to manage the plugins, it is not a part of any plugin itself.

    .. php:attr:: name

        string

        Directory name for the plugin.

    .. php:attr:: active

        int

        Whether this plugin is active.

    .. php:attr:: version

        string

        Version string for the currently-installed plugin.

    .. php:attr:: _displayName

        protected string

        Human-readable display name of the plugin.

    .. php:attr:: _author

        protected string

        The plugin's author.

    .. php:attr:: _description

        protected string

        Description of the plugin.

    .. php:attr:: _link

        protected string

        URL for documentation or further information about the plugin.

    .. php:attr:: _loaded

        protected boolean

        Whether the plugin has been loaded.

    .. php:attr:: _hasConfig

        protected boolean

        Whether the plugin has a custom configuration form.

    .. php:attr:: _requiredPlugins

        protected array

        Directory names of required plugins.

    .. php:attr:: _optionalPlugins

        protected array

        Directory names of optional plugins.

    .. php:attr:: _minimumOmekaVersion

        protected string

        Minimum Omeka version requirement for the plugin.

    .. php:attr:: _testedUpToVersion

        protected string

        Maximum version of Omeka that the plugin has been tested on.

    .. php:attr:: _iniVersion

        protected string

        Version of the plugin that is stored in the INI.

    .. php:attr:: _iniTags

        protected array

        List of tags associated with this plugin, as retrieved from
        the ini file.

    .. php:method:: _validate()

        Validate the plugin.

        The directory name must be set.

    .. php:method:: getDirectoryName()

        Get the name of the directory containing the plugin.

        :returns: string

    .. php:method:: setDirectoryName($name)

        Set the name of the directory containing the plugin.

        :type $name: string
        :param $name:
        :returns: Plugin

    .. php:method:: getDisplayName()

        Get the human-readable name of the plugin.

        If there is no human-readable name available, returns the directory name
        instead.

        :returns: string

    .. php:method:: setDisplayName($name)

        Set the human-readable name of the plugin.

        :type $name: string
        :param $name:
        :returns: Plugin

    .. php:method:: getAuthor()

        Get the plugin's author.

        :returns: string

    .. php:method:: setAuthor($author)

        Set the author's name.

        :type $author: string
        :param $author:
        :returns: Plugin

    .. php:method:: getDescription()

        Get the description of the plugin.

        :returns: string

    .. php:method:: setDescription($description)

        Set the description of the plugin.

        :type $description: string
        :param $description:
        :returns: Plugin

    .. php:method:: getMinimumOmekaVersion()

        Get the minimum version of Omeka that this plugin requires to work.

        :returns: string

    .. php:method:: setMinimumOmekaVersion($version)

        Set the minimum required version of Omeka.

        :type $version: string
        :param $version:
        :returns: Plugin

    .. php:method:: getTestedUpToOmekaVersion()

        Get the version of Omeka that this plugin is tested up to.

        :returns: string

    .. php:method:: setTestedUpToOmekaVersion($version)

        Set the version of Omeka that this plugin is tested up to.

        :type $version: string
        :param $version:
        :returns: Plugin

    .. php:method:: getRequiredPlugins()

        Get the list of plugins that are required for this plugin to work.

        :returns: array

    .. php:method:: setRequiredPlugins($plugins)

        Set the list of plugins that are required for this plugin to work.

        :param $plugins:
        :returns: Plugin

    .. php:method:: getOptionalPlugins()

        Get the list of plugins that can be used, but are not required by, this
        plugin.

        :returns: array

    .. php:method:: setOptionalPlugins($plugins)

        Set the list of optional plugins.

        :param $plugins:
        :returns: Plugin

    .. php:method:: getIniTags()

        Get the list of tags for this plugin (from the ini file).

        :returns: array

    .. php:method:: setIniTags($tags)

        Set the list of tags for this plugin.

        :param $tags:
        :returns: Plugin

    .. php:method:: getSupportLinkUrl()

        Get the support link url from plugin.ini

        :returns: string

    .. php:method:: setSupportLinkUrl($link)

        Set the support link url from plugin.ini

        :param $link:
        :returns: Plugin

    .. php:method:: getLinkUrl()

        Get the URL link from the plugin.ini.

        :returns: string

    .. php:method:: setLinkUrl($link)

        Set the link from the plugin.ini.

        :type $link: string
        :param $link:
        :returns: Plugin

    .. php:method:: isInstalled()

        Determine whether the Plugin has been installed.

        :returns: bool

    .. php:method:: isLoaded()

        Determine whether the Plugin has been loaded.

        :returns: bool

    .. php:method:: setLoaded($flag)

        Set whether the plugin has been loaded.

        :type $flag: bool
        :param $flag:
        :returns: Plugin

    .. php:method:: isActive()

        Determine whether the plugin is active.

        :returns: bool

    .. php:method:: setActive($flag)

        Set whether the plugin is active.

        :type $flag: bool
        :param $flag:
        :returns: Plugin

    .. php:method:: hasConfig()

        Determine whether the plugin has a custom configuration form.

        :returns: bool

    .. php:method:: setHasConfig($flag)

        Set whether the plugin has a custom configuration form.

        :type $flag: bool
        :param $flag:
        :returns: Plugin

    .. php:method:: getIniVersion()

        Get the version of the plugin stored in the INI file.

        :returns: string

    .. php:method:: setIniVersion($version)

        Set the version of the plugin that is indicated by the INI file.

        :type $version: string
        :param $version:
        :returns: Plugin

    .. php:method:: getDbVersion()

        Get the version of the plugin that is stored in the database.

        :returns: string

    .. php:method:: setDbVersion($version)

        Set the version of the plugin that is stored in the database.

        :type $version: string
        :param $version:
        :returns: Plugin

    .. php:method:: hasNewVersion()

        Determine whether there is a new version of the plugin available.

        :returns: bool

    .. php:method:: meetsOmekaMinimumVersion()

        Determine whether this Omeka install meets the plugin's minimum version
        requirements.

        If the field is not set, assume that it meets the requirements.  If the
        field is set, it must be greater than the current version of Omeka.

        :returns: bool

    .. php:method:: meetsOmekaTestedUpToVersion()

        Determine whether this Omeka version has been tested for use with the
        plugin.

        :returns: bool

    .. php:method:: getResourceId()

        Declare the Plugin model as relating to the Plugins ACL resource.

        :returns: string
