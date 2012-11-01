#######
install
#######

*****
Usage
*****

This hook is primarily used to set options to the database and create tables, and any other initial actions required for your plugin to function, such as initial records or setting options. 

*********
Arguments
*********

None

********
Examples
********


.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('install');
        
        protected $_options = array('simple_pages_filter_page_content' => '0');
            
        function hookInstall()
        {
            // Create the table.
            $db = get_db();
            $sql = "
            CREATE TABLE IF NOT EXISTS `$db->SimplePagesPage` (
              `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
              `modified_by_user_id` int(10) unsigned NOT NULL,
              `created_by_user_id` int(10) unsigned NOT NULL,
              `is_published` tinyint(1) NOT NULL,
              `title` tinytext COLLATE utf8_unicode_ci NOT NULL,
              `slug` tinytext COLLATE utf8_unicode_ci NOT NULL,
              `text` text COLLATE utf8_unicode_ci,
              `updated` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
              `inserted` timestamp NOT NULL DEFAULT '0000-00-00 00:00:00',
              `order` int(10) unsigned NOT NULL,
              `parent_id` int(10) unsigned NOT NULL,
              `template` tinytext COLLATE utf8_unicode_ci NOT NULL,
              `use_tiny_mce` tinyint(1) NOT NULL,
              PRIMARY KEY (`id`),
              KEY `is_published` (`is_published`),
              KEY `inserted` (`inserted`),
              KEY `updated` (`updated`),
              KEY `created_by_user_id` (`created_by_user_id`),
              KEY `modified_by_user_id` (`modified_by_user_id`),
              KEY `order` (`order`),
              KEY `parent_id` (`parent_id`)
            ) ENGINE=InnoDB  DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci";
            $db->query($sql);
            
            // Save an example page.
            $page = new SimplePagesPage;
            $page->modified_by_user_id = current_user()->id;
            $page->created_by_user_id = current_user()->id;
            $page->is_published = 1;
            $page->parent_id = 0;
            $page->title = 'About';
            $page->slug = 'about';
            $page->text = '<p>This is an example page. Feel free to replace this content, or delete the page and start from scratch.</p>';
            $page->save();
    
            $this->_installOptions();
        }
    
    }