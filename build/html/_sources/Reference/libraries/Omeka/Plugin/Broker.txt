-------------------
Omeka_Plugin_Broker
-------------------

.. php:class:: Omeka_Plugin_Broker

    Package: :doc:`Plugin\\Broker </Reference/packages/Plugin/Broker/index>`

    Plugin Broker for Omeka.
    
    For example,$broker->callHook('add_action_contexts', array('controller' => $controller))would call the 'add_action_contexts' on all plugins, and it would provide thecontroller object as the first argument to all implementations of that hook.

    .. php:attr:: _callbacks
    
        Array of hooks that have been implemented for plugins.

    .. php:attr:: _filters
    
        Stores all defined filters.
        
        Storage in array where $_filters['filterName']['priority']['plugin'] = $hook;

    .. php:attr:: _current
    
        The directory name of the current plugin (used for calling hooks)

    .. php:method:: addHook(string $hook, string $callback, string|null $plugin)
    
        Add a hook implementation for a plugin.
        
        :param string $hook: Name of the hook being implemented.
        :param string $callback: PHP callback for the hook implementation.
        :param string|null $plugin: Optional name of the plugin for which to add the hook. If omitted, the current plugin is used.
        :returns: void

    .. php:method:: getHook(string $pluginDirName, string $hook)
    
        Get the hook implementation for a plugin.
        
        :param string $pluginDirName: Name of the plugin to get the implementation from.
        :param string $hook: Name of the hook to get the implementation for.
        :returns: callback|null

    .. php:method:: setCurrentPluginDirName(string $pluginDirName)
    
        Set the currently-focused plugin by directory name.
        
        The plugin helper functions do not have any way of determining whatplugin to is currently in focus.  These get/setCurrentPluginDirNamemethods allow the broker to know how to delegate to specific plugins ifnecessary.
        
        :param string $pluginDirName: Plugin to set as current.
        :returns: void

    .. php:method:: getCurrentPluginDirName()
    
        Get the directory name of the currently-focused plugin.
        
        :returns: string

    .. php:method:: callHook(string $name, array $args = Array, Plugin|string $plugin)
    
        Call a hook by name.
        
        Hooks can either be called globally or for a specific plugin only.
        
        :param string $name: The name of the hook.
        :param array $args: Arguments to be passed to the hook implementations.
        :param Plugin|string $plugin: Name of the plugin that will invoke the hook.
        :returns: void

    .. php:method:: addFilter(string|array $name, callback $callback, $priority = 10)
    
        Add a filter implementation.
        
        :param string|array $name: Name of filter being implemented.
        :param callback $callback: PHP callback for filter implementation.
        :param unknown $priority: 
        :returns: void

    .. php:method:: _getFilterNamespace()
    
        Retrieve the namespace to use for the filter to be added.
        
        :returns: string Name of the current plugin (if applicable). Otherwise, a magic constant that denotes globally applied filters.

    .. php:method:: _getFilterKey(string|array $name)
    
        Retrieve the key used for indexing the filter. The filter name should be
        either a string or an array of strings. If the filter name is an object,
        that might cause fiery death when using the serialized value for an array
        key.
        
        :param string|array $name: Filter name.
        :returns: string Key for filter indexing.

    .. php:method:: getFilters(string|array $hookName)
    
        Return all the filters for a specific hook in the correct order of
        execution.
        
        :param string|array $hookName: Filter name.
        :returns: array Indexed array of filter callbacks.

    .. php:method:: clearFilters(string|null $name)
    
        Clear all implementations for a filter (or all filters).
        
        :param string|null $name: The name of the filter to clear.  If null or omitted, all filters will be cleared.
        :returns: void

    .. php:method:: applyFilters(mixed $name, mixed $value, array $args = Array)
    
        Run an arbitrary value through a set of filters.
        
        :param mixed $name: The filter name.
        :param mixed $value: The value to filter.
        :param array $args: Additional arguments to pass to filter implementations.
        :returns: mixed Result of applying filters to $value.

    .. php:method:: register()
    
        Register the plugin broker so that plugin writers can use global functions
        like add_plugin_hook() to interact with the plugin API.
        
        :returns: void