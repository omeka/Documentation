######
config
######

*****
Usage
*****

This hook processes posted data from the configuration form created by the config_form hook. Most use cases will involve setting configuration options to the database using set_option().

Both the config and config_form hooks must be used to creating a configuration form for a plugin. 

*********
Arguments
*********

``array`` post
    The post data

********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('config');
                
         /**
         * Set the options from the config form input.
         */
        function hookConfig()
        {
            set_option('simple_pages_filter_page_content', (int)(boolean)$_POST['simple_pages_filter_page_content']);
        }
    }