.. _understandingomekapluginabstractplugin:

#########################################
Understanding Omeka_Plugin_AbstractPlugin
#########################################


:php:class:`Omeka_Plugin_AbstractPlugin` is designed to streamline common tasks for a plugin, such as defining hook and filter callbacks and setting options when the plugin is installed.

To use it, simply create a class for your plugin as its own file in the plugins directory:

.. code-block:: php
    
    // In plugins/YourPlugin/YourPluginPlugin.php
    class YourPluginPlugin extends Omeka_Plugin_AbstractPlugin
    {}
    
Hook and filter callbacks are defined with an array. One change introduced in Omeka 2.0 is arbitrary hook and filter callback names. Before, all callback names followed a predetermined format. While this format remains an option, now a corresponding key in ``$_hooks`` and ``$_filters`` will be interpreted as the name of the callback method.

.. code-block:: php

    protected $_filters = array('admin_navigation_main', 
      'public_navigation_main', 
      'changeSomething' => 'display_setting_site_title', 
      'displayItemDublinCoreTitle' => array(
          'Display', 
          'Item', 
          'Dublin Core', 
          'Title', 
      ));
      
      protected $_hooks = array('install', 'uninstall'); 
      
      
When installing your plugin, there might be options that need to be set. You can do this easily within the install callback by adding an ``$_options`` array and calling :php:meth:`Omeka_Plugin_AbstractPlugin::_installOptions` from the install callback, and :php:meth:`Omeka_Plugin_AbstractPlugin::_installOptions` in the uninstall callback. The array is name-value pairs for the name of the option and initial value.

.. code-block:: php

    protected $_hooks = array('install', 'uninstall');

    protected $_options = array('my_plugin_option'=>'option_value');
    
    public function install() {        
        $this->_installOptions();    
    }
    
    public function uninstall() {        
        $this->_uninstallOptions();    
    }    
    
    
    
When creating tables for your plugin in the install hook, use the ``_db`` property. Omeka will convert your model names into the appropriate table names.   

.. code-block:: php

    public function hookInstall() {
        $db = $this->_db;
        $sql = "
        CREATE TABLE IF NOT EXISTS `$db->MyPluginModel` (
          `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
          `modified_by_user_id` int(10) unsigned NOT NULL,
          . . . 
          ) ENGINE=InnoDB  DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci";
        $db->query($sql);
        
    }