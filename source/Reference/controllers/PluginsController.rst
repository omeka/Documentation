-----------------
PluginsController
-----------------

.. php:class:: PluginsController

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    .. php:method:: init()

    .. php:method:: configAction()
    
        Load the configuration form for a specific plugin.  
        That configuration form will be POSTed back to this URL and processed by 
        the plugin.
        
        :returns: void

    .. php:method:: installAction()

    .. php:method:: activateAction()
    
        Action to activate a plugin
        
        :returns: void

    .. php:method:: deactivateAction()
    
        Action to deactivate a plugin
        
        :returns: void

    .. php:method:: upgradeAction()

    .. php:method:: browseAction()
    
        Action to browse plugins
        
        :returns: void

    .. php:method:: uninstalledAction()
    
        Action to browse only uninstalled plugins
        
        :returns: void

    .. php:method:: activeAction()
    
        Action to browse only uninstalled plugins
        
        :returns: void

    .. php:method:: inactiveAction()

    .. php:method:: uninstallAction()
    
        Action to uninstall a plugin
        
        :returns: void

    .. php:method:: deleteAction()

    .. php:method:: addAction()

    .. php:method:: _getPluginByName(boolean $create = )
    
        Retrieve the Plugin record based on the name passed via the request.
        
        :param boolean $create: Whether or not the plugin object should be created if it has not already been loaded.