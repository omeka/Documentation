------------------------
Omeka_Test_Helper_Plugin
------------------------

Package: :doc:`Test\\Helper </Reference/packages/Test/Helper/index>`

.. php:class:: Omeka_Test_Helper_Plugin

    Encapsulates testing functionality for Omeka plugins.

    .. php:method:: setUp($pluginName)

        Install and initialize a plugin.

        Note: Normally used in the setUp() method of plugin tests.

        :type $pluginName: string
        :param $pluginName:

    .. php:method:: install($pluginName)

        Install a plugin

        :type $pluginName: string
        :param $pluginName: The name of the plugin to install.
        :returns: Plugin

    .. php:method:: initialize($pluginName = null)

        Initializes the plugin hooks and filters fired in the core resources for a
        plugin
        Note: Normally used in the setUp() function of the subclasses that test
        plugins.

        :type $pluginName: string
        :param $pluginName: If omitted, initialize all installed plugins.
        :returns: void

    .. php:method:: _defineResponseContexts()

        Run the response_contexts filter.

        :returns: void

    .. php:method:: setPluginLoader($pluginLoader)

        Set the plugin loader for the helper to use.

        :type $pluginLoader: Omeka_Plugin_Loader
        :param $pluginLoader:

    .. php:method:: setPluginIniReader($pluginIniReader)

        Set the plugin INI reader for the helper to use.

        :type $pluginIniReader: Omeka_Plugin_Ini
        :param $pluginIniReader:

    .. php:method:: setPluginBroker($pluginBroker)

        Set the plugin broker for the helper to use.

        :type $pluginBroker: Omeka_Plugin_Broker
        :param $pluginBroker:

    .. php:method:: setAcl($acl)

        Set the ACL for the helper to use.

        :type $acl: Zend_Acl
        :param $acl:

    .. php:method:: setRouter($router)

        Set the router for the helper to use.

        :type $router: Zend_Controller_Router_Interface
        :param $router:

    .. php:method:: __get($name)

        Lazy-loading for helper properties.

        When a property is not set, attempts to load a default through standard
        Omeka global state.  If this state is unavailable or undesireable,
        use the set*() methods before calling any of the other public methods of
        this class.

        :param $name:
        :returns: mixed
