###################
public_theme_header
###################

*****
Usage
*****

Adds content to the ``<head>`` element. Usually used to add javascript and/or css via the :php:func:`queue_js` or :php:fun:`queue_css` functions

*********
Arguments
*********

:php:class:`Omeka_View` view
    The view object


********
Examples
********

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_Abstract
    {
        protected $_hooks = array('public_theme_header');
    
        public function hookPublicThemeHeader($args)
        {
            queue_css('myplugin'); // assumes myplugin has a /views/public/css/myplugin.css file
        }    
    }


********
See Also
********

:php:fun:`queue_css`
:php:fun:`queue_js`