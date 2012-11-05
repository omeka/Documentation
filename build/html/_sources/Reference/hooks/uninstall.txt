#########
uninstall
#########

*****
Usage
*****

Runs when a plugin is uninstalled to remove database tables, settings, etc.

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
        protected $_hooks = array('uninstall');
        
        function hookUninstall()
        {        
            // Drop the table.
            $db = get_db();
            $sql = "DROP TABLE IF EXISTS `$db->SimplePagesPage`";
            $db->query($sql);
    
            $this->_uninstallOptions();
        }   
    
    }


