-------------------
Omeka_Plugin_Broker
-------------------

Package: :doc:`Plugin\\Broker </Reference/packages/Plugin/Broker/index>`

.. php:class:: Omeka_Plugin_Broker

    Plugin Broker for Omeka.

    For example,
    $broker->callHook('add_action_contexts', array('controller' => $controller))
    would call the 'add_action_contexts' on all plugins, and it would provide the controller object as the first argument to all implementations of that hook.

    .. php:attr:: _callbacks

        protected array

        Array of hooks that have been implemented for plugins.

    .. php:attr:: _filters

        protected array

        Stores all defined filters.

        Storage in array where $_filters['filterName']['priority']['plugin'] =
        $hook;

    .. php:attr:: _current

        protected string

        The directory name of the current plugin (used for calling hooks)

    .. php:method:: addHook($hook, $callback, $plugin = null)

        Add a hook implementation for a plugin.

        :type $hook: string
        :param $hook: Name of the hook being implemented.
        :type $callback: string
        :param $callback: PHP callback for the hook implementation.
        :type $plugin: string|null
        :param $plugin: Optional name of the plugin for which to add the hook. If omitted, the current plugin is used.
        :returns: void

    .. php:method:: getHook($pluginDirName, $hook)

        Get the hook implementation for a plugin.

        :type $pluginDirName: string
        :param $pluginDirName: Name of the plugin to get the implementation from.
        :type $hook: string
        :param $hook: Name of the hook to get the implementation for.
        :returns: callback|null

    .. php:method:: setCurrentPluginDirName($pluginDirName)

        Set the currently-focused plugin by directory name.

        The plugin helper functions do not have any way of determining what plugin
        to is currently in focus.  These get/setCurrentPluginDirName methods allow
        the broker to know how to delegate to specific plugins if necessary.

        :type $pluginDirName: string
        :param $pluginDirName: Plugin to set as current.
        :returns: void

    .. php:method:: getCurrentPluginDirName()

        Get the directory name of the currently-focused plugin.

        :returns: string

    .. php:method:: callHook($name, $args = array(), $plugin = null)

        Call a hook by name.

        Hooks can either be called globally or for a specific plugin only.

        :type $name: string
        :param $name: The name of the hook.
        :type $args: array
        :param $args: Arguments to be passed to the hook implementations.
        :type $plugin: Plugin|string
        :param $plugin: Name of the plugin that will invoke the hook.
        :returns: void

    .. php:method:: addFilter($name, $callback, $priority = 10)

        Add a filter implementation.

        :type $name: string|array
        :param $name: Name of filter being implemented.
        :type $callback: callback
        :param $callback: PHP callback for filter implementation.
        :param $priority:
        :returns: void

    .. php:method:: _getFilterNamespace()

        Retrieve the namespace to use for the filter to be added.

        :returns: string Name of the current plugin (if applicable). Otherwise, a magic constant that denotes globally applied filters.

    .. php:method:: _getFilterKey($name)

        Retrieve the key used for indexing the filter. The filter name should be
        either a string or an array of strings. If the filter name is an object,
        that might cause fiery death when using the serialized value for an array
        key.

        :type $name: string|array
        :param $name: Filter name.
        :returns: string Key for filter indexing.

    .. php:method:: getFilters($hookName)

        Return all the filters for a specific hook in the correct order of
        execution.

        :type $hookName: string|array
        :param $hookName: Filter name.
        :returns: array Indexed array of filter callbacks.

    .. php:method:: clearFilters($name = null)

        Clear all implementations for a filter (or all filters).

        :type $name: string|null
        :param $name: The name of the filter to clear.  If null or omitted, all filters will be cleared.
        :returns: void

    .. php:method:: applyFilters($name, $value, $args = array())

        Run an arbitrary value through a set of filters.

        :type $name: mixed
        :param $name: The filter name.
        :type $value: mixed
        :param $value: The value to filter.
        :type $args: array
        :param $args: Additional arguments to pass to filter implementations.
        :returns: mixed Result of applying filters to $value.

    .. php:method:: register()

        Register the plugin broker so that plugin writers can use global functions
        like add_plugin_hook() to interact with the plugin API.

        :returns: void
