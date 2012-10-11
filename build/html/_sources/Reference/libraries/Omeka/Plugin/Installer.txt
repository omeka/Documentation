----------------------
Omeka_Plugin_Installer
----------------------

.. php:class:: Omeka_Plugin_Installer

    Changes the state of any given plugin (installed/uninstalled/activated/deactivated)

    .. php:attr:: _broker
    
        Plugin broker object.

    .. php:attr:: _loader
    
        Plugin loader object.

    .. php:method:: __construct(Omeka_Plugin_Broker $broker, Omeka_Plugin_Loader $loader)
    
        :param Omeka_Plugin_Broker $broker: Plugin broker object.
        :param Omeka_Plugin_Loader $loader: Plugin loader object.

    .. php:method:: activate(Plugin $plugin)
    
        Activate a plugin.
        
        :param Plugin $plugin: Plugin to activate.
        :returns: void

    .. php:method:: deactivate(Plugin $plugin)
    
        Deactivate a plugin.
        
        :param Plugin $plugin: Plugin to deactivate.
        :returns: void

    .. php:method:: upgrade(Plugin $plugin)
    
        Upgrade a plugin.
        
        This will activate the plugin, then run the 'upgrade' hook.
        
        :param Plugin $plugin: Plugin to upgrade.
        :returns: void

    .. php:method:: install(Plugin $plugin)
    
        Install a plugin.
        
        This will activate the plugin, then run the 'install' hook.
        
        :param Plugin $plugin: Plugin to install.
        :returns: void

    .. php:method:: uninstall(Plugin $plugin)
    
        Uninstall a plugin.
        
        This will run the 'uninstall' hook for the given plugin, and then itwill remove the entry in the DB corresponding to
        the plugin.
        
        :param Plugin $plugin: Plugin to uninstall.
        :returns: void