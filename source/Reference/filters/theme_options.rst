#############
theme_options
#############

*****
Usage
*****

Filters the theme configuration options before they are returned by a call to :php:func:`get_theme_option`.

Plugins can use this filter to modify settings for particular themes, or store and use alternative settings.

The options will be provided as a serialized string, so in order to modify the options, a plugin must unserialize() the array, make whatever changes are desired, then serialize() again before returning. 

*****
Value
*****

``string`` $themeOptions

    The set of all theme configuration options for a theme. This is a serialized array. 

*********
Arguments
*********

``string`` theme_name

    The name of the theme

********
Examples
********

Exhibit Builder adds theme settings on a per-exhibit basis.


.. code-block:: php

    class ExhibitBuilderPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('theme_options');
        
        public filterThemeOptions($options, $args)
        {
            if (Omeka_Context::getInstance()->getRequest()->getModuleName() == 'exhibit-builder' && function_exists('__v')) {
                if ($exhibit = exhibit_builder_get_current_exhibit()) {
                    $exhibitThemeOptions = $exhibit->getThemeOptions();
                }
            }
            if (!empty($exhibitThemeOptions)) {
                return serialize($exhibitThemeOptions);
            }
            return $themeOptions;
        }    
    }
