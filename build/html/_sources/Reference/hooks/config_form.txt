###########
config_form
###########

*****
Usage
*****

This hook runs when the 'Configure' button is clicked for a specific plugin on the admin plugins panel.

Plugins use this hook to directly output the HTML that goes inside the <form> tag for the configuration form.

The config hook is used to process the submitted data from the form that was created with this hook. 

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
        protected $_hooks = array('config_form');
               
        /**
         * Display the plugin config form.
         */
        function hookConfigForm()
        {
            require dirname(__FILE__) . '/config_form.php';
        }
    }
