#######
upgrade
#######

*****
Usage
*****

When Omeka detects that a user has installed a new version of the plugin, it automatically deactivates the plugin and presents an "Upgrade" button. This hook runs when a superuser clicks the "Upgrade" button. It is primarily used to migrate database tables and other data stored by older versions of the plugin. 

*********
Arguments
*********

``string`` old_version
    The previous version that was installed and is being upgraded from.
     
``string`` new_version
    The new, current version of the plugin. 

********
Examples
********

.. code-block: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('upgrade');
        
        public function hookUpgrade($args)
        {
            $oldVersion = $args['old_version'];
            $newVersion = $args['new_version'];
            
            switch($oldVersion)
            {
                // let the plugin cascade its upgrades
                case '1.0':
                // code to upgrade from 1.0 to 1.1
                case '1.1':
                // code to upgrade from 1.1 to 2.0
                case '2.0':
                // code to upgrade from 2.0 to 2.1
            }                
        }
    }
    
    
.. code-block: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('upgrade');
        
        function hookUpgrade($args)
        {
            $oldVersion = $args['old_version'];
            $newVersion = $args['new_version'];
            $db = get_db();
            
            if ($oldVersion < '1.0') {
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `is_published` )";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `inserted` ) ";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `updated` ) ";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `add_to_public_nav` ) ";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `created_by_user_id` ) ";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `modified_by_user_id` ) ";
                $db->query($sql);    
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD `order` INT UNSIGNED NOT NULL ";
                $db->query($sql);
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `order` ) ";
                $db->query($sql);
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD `parent_id` INT UNSIGNED NOT NULL ";
                $db->query($sql);
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD INDEX ( `parent_id` ) ";
                $db->query($sql);
                
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD `template` TINYTEXT CHARACTER SET utf8 COLLATE utf8_unicode_ci NOT NULL ";
                $db->query($sql);
            }
    
            if ($oldVersion < '1.3') {
                $sql = "ALTER TABLE `$db->SimplePagesPage` ADD `use_tiny_mce` TINYINT(1) NOT NULL";
                $db->query($sql);
            }
    
            if ($oldVersion < '2.0') {
                $db->query("ALTER TABLE `$db->SimplePagesPage` DROP `add_to_public_nav`");
                delete_option('simple_pages_home_page_id');
            }
        }   
    }    
    
 
    
    
    
    
    
