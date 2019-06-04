##########################
html_purifier_config_setup
##########################

.. versionadded:: 2.7

*****
Usage
*****

Alters the configuration settings for the HTMLPurifier library.

*****
Value
*****

``HTMLPurifier_Config`` $purifierConfig
    The config object for HTMLPurifier

*********
Arguments
*********

``array`` defaults
    The default configuration keys (these have already been set to the passed config object)
``array`` allowedHtmlElements
    List of user-configured enabled elements
``array`` allowedHtmlAttributes
    List of user-configured enabled attributes

********
Examples
********

Force a prefix on all user-provided ``id`` attributes (for other options see the HTMLPurifier
documentation pages linked below:

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
        protected $_filters = array('html_purifier_config_setup');
        
        public filterHtmlPurifierConfigSetup($purifierConfig, $args)
        {
            $purifierConfig->set('Attr.IDPrefix', 'foo_');
            return $purifierConfig;
        }    
    }


********
See Also
********

- `HTMLPurifier customization documentation <http://htmlpurifier.org/docs/enduser-customize.html>`_

- `HTMLPurifier list of configuration options <http://htmlpurifier.org/live/configdoc/plain.html>`_


