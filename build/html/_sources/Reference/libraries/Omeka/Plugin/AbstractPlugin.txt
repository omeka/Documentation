---------------------------
Omeka_Plugin_AbstractPlugin
---------------------------

.. php:class:: Omeka_Plugin_AbstractPlugin

    Abstract plugin class.
    
    Plugin authors may inherit from this class to aid in building their plugin framework.

    .. php:attr:: _db
    
        Database object accessible to plugin authors.

    .. php:attr:: _hooks
    
        Plugin hooks.
        
        In the child class plugin authors should set an array containing hook names as values and, optionally, callback
        names as keys. If a callback name is given, the child class should contain an identically named method. If no
        callback key is given, the child class should contain a corresponding hookCamelCased() method. E.g: the
        after_save_form_record filter should have a corresponding hookAfterSaveRecord() method.
        
        For example:
        .. code-block:: php 
        
             array('install', 
                   'uninstall', 
                   'doSomething' => 'after_save_item')

    .. php:attr:: _filters
    
        Plugin filters.
        
        In the child class plugin authors should set an array containing filter names as values and, optionally, callback
        names as keys. If a callback name is given, the child class should contain an identically named method. If no
        callback key is given, the child class should contain a corresponding filterCamelCased() method. E.g: the
        admin_navigation_main filter should have a corresponding filterAdminNavigationMain() method.
        
        For example:
        .. code-block:: php 
        
             array('admin_navigation_main', 
                   'public_navigation_main', 
                   'changeSomething' => 'display_option_site_title', 
                   'displayItemDublinCoreTitle' => array('Display', 'Item', 'Dublin Core', 'Title'))

    .. php:attr:: _options
    
        Plugin options.
        
        Plugin authors should give an array containing option names as keys and their default values as values, if any.
        
        For example:
        .. code-block:: php 
        
             array('option_name1' => 'option_default_value1',
                   'option_name2' => 'option_default_value2',
                   'option_name3',
                   'option_name4')

    .. php:method:: __construct()
    
        Construct the plugin object.
        
        Sets the database object. Plugin authors must call parent::__construct()
        in the child class's constructor, if used.

    .. php:method:: setUp()
    
        Set up the plugin to hook into Omeka.
        
        Adds the plugin's hooks and filters. Plugin writers must call this method after instantiating their plugin class.

    .. php:method:: _installOptions()
    
        Set options with default values.
        
        Plugin authors may want to use this convenience method in their install hook callback.

    .. php:method:: _uninstallOptions()
    
        Delete all options.
        
        Plugin authors may want to use this convenience method in their uninstall hook callback.

    .. php:method:: _addHooks()
    
        Validate and add hooks.

    .. php:method:: _addFilters()
    
        Validate and add filters.