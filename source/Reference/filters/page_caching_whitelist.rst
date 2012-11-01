######################
page_caching_whitelist
######################

*****
Usage
*****


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
        protected $_filters = array('page_caching_whitelist');
    
        /**
         * Specify the default list of urls to whitelist
         * 
         * @param $whitelist array An associative array urls to whitelist, 
         * where the key is a regular expression of relative urls to whitelist 
         * and the value is an array of Zend_Cache front end settings
         * @return array The whitelist
         */
        function filterPageCachingWhitelist($whitelist)
        {
            // Add custom routes based on the page slug.
            $pages = get_db()->getTable('SimplePagesPage')->findAll();
            foreach($pages as $page) {
                $whitelist['/' . trim($page->slug, '/')] = array('cache'=>true);
            }
                
            return $whitelist;
        }    
    
    }