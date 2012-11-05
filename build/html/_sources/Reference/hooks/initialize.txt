##########
initialize
##########

*****
Usage
*****

This hook runs during every request on installed/activated plugins. It is primarily used to modify the runtime behavior of Omeka for every request and response. 

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
        protected $_hooks = array('initialize');
            
        function hookInitialize()
        {
            add_translation_source(dirname(__FILE__) . '/languages');
        }        

    }
    
    