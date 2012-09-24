--------------------
Omeka_Plugin_Factory
--------------------

.. php:class:: Omeka_Plugin_Factory

    Responsible for creating a set of Plugin records corresponding to plugins 
    that have not been installed yet.

    .. php:attr:: _basePath
    
        Base path for plugins; the plugin directory

    .. php:method:: __construct(string $basePath)
    
        :param string $basePath: Plugin base directory.

    .. php:method:: getNewPlugins(array $existingPlugins)
    
        Retrieve all new plugins in the plugin directory.
        
        :param array $existingPlugins: An array of existing Plugin objects.
        :returns: array An array of Plugin objects for the new plugins.

    .. php:method:: _getDirectoryList()
    
        Retrieve an array of all the plugins in the plugin directory.
        A plugin is considered to be present when a directory includes a
        plugin.php file or has a valid plugin class.
        
        :returns: array A list of valid plugin directory names.

