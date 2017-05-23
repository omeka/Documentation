######
config
######

*****
Usage
*****

This hook processes posted data from the configuration form created by the config_form hook. Most use cases will involve setting configuration options to the database using set_option().

Both the config and config_form hooks must be used to creating a configuration form for a plugin.

To reject the passed configuration and report an error to the user, throw an
:php:exc:`Omeka_Validate_Exception`.

*********
Arguments
*********

``array`` post
    The post data

********
Examples
********

.. code-block:: php

    class ExamplePlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('config', 'config_form');

        /* --snip-- */

        /**
         * Set the options from the config form input.
         */
        function hookConfig($args)
        {
            set_option('example_plugin_setting', $args['post']['example_plugin_setting']);
        }
    }

********
See Also
********

* :doc:`config_form`
