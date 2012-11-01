##########
define_acl
##########

*****
Usage
*****

This hook runs when Omeka's ACL is instantiated. It allows plugin writers to manipulate the ACL that controls user access in Omeka.

In general, plugins use this hook to restrict and/or allow access for specific user roles to the pages that it creates. 

*********
Arguments
*********

``array`` acl
    The Zend_Acl object

********
Examples
********



.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('define_acl');
                
        function hookDefineAcl($args)
        {
            $acl = $args['acl'];
            
            $indexResource = new Zend_Acl_Resource('SimplePages_Index');
            $pageResource = new Zend_Acl_Resource('SimplePages_Page');
            $acl->add($indexResource);
            $acl->add($pageResource);
    
            $acl->allow(array('super', 'admin'), array('SimplePages_Index', 'SimplePages_Page'));
            $acl->allow(null, 'SimplePages_Page', 'show');
            $acl->deny(null, 'SimplePages_Page', 'show-unpublished');
        }     

    }