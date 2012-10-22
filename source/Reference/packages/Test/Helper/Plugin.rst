------------------------
Omeka_Test_Helper_Plugin
------------------------

.. php:class:: Omeka_Test_Helper_Plugin

    Package: :doc:`/Reference/packages/Test\Helper/index`

    Encapsulates testing functionality for Omeka plugins.

    .. php:method:: setUp(string $pluginName)
    
        Install and initialize a plugin.
        
        Note: Normally used in the setUp() method of plugin tests.
        
        :param string $pluginName:

    .. php:method:: install(string $pluginName)
    
        Install a plugin
        
        :param string $pluginName: The name of the plugin to install.
        :returns: Plugin

    .. php:method:: initialize(string $pluginName)
    
        Initializes the plugin hooks and filters fired in the core resources for a plugin
        Note: Normally used in the setUp() function of the subclasses that test plugins.
        
        :param string $pluginName: If omitted, initialize all installed plugins.
        :returns: void

    .. php:method:: _defineResponseContexts()
    
        Run the define_response_contexts filter.
        
        :returns: void

    .. php:method:: setPluginLoader(Omeka_Plugin_Loader $pluginLoader)
    
        Set the plugin loader for the helper to use.
        
        :param Omeka_Plugin_Loader $pluginLoader:

    .. php:method:: setPluginIniReader(Omeka_Plugin_Ini $pluginIniReader)
    
        Set the plugin INI reader for the helper to use.
        
        :param Omeka_Plugin_Ini $pluginIniReader:

    .. php:method:: setPluginBroker(Omeka_Plugin_Broker $pluginBroker)
    
        Set the plugin broker for the helper to use.
        
        :param Omeka_Plugin_Broker $pluginBroker:

    .. php:method:: setAcl(Zend_Acl $acl)
    
        Set the ACL for the helper to use.
        
        :param Zend_Acl $acl:

    .. php:method:: setRouter(Zend_Controller_Router_Interface $router)
    
        Set the router for the helper to use.
        
        :param Zend_Controller_Router_Interface $router:

    .. php:method:: __get($name)
    
        Lazy-loading for helper properties.
        
        When a property is not set, attempts to load a default through standardOmeka global state.  If this state is
        unavailable or undesireable,use the set*() methods before calling any of the other public methodsof this class.
        
        :param unknown $name: 
        :returns: mixed