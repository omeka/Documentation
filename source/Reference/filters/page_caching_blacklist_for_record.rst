######################
page_caching_blacklist
######################


*****
Usage
*****

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record
    The record being saved



``string`` action
    The action taking place



********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('page_caching_blacklist');
        
        /**
         * Add pages to the blacklist
         * 
         * @param $blacklist array An associative array urls to blacklist, 
         * where the key is a regular expression of relative urls to blacklist 
         * and the value is an array of Zend_Cache front end settings
         * @param $record
         * @param $args Filter arguments. contains:
         * - record: the record
         * - action: the action
         * @return array The blacklist
         */
        function filterPageCachingBlacklistForRecord($blacklist, $args)
        {
            $record = $args['record'];
            $action = $args['action'];
    
            if ($record instanceof SimplePagesPage) {
                $page = $record;
                if ($action == 'update' || $action == 'delete') {
                    $blacklist['/' . trim($page->slug, '/')] = array('cache'=>false);
                }
            }
                
            return $blacklist;
        }
    }