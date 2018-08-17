###########
public_head
###########

*****
Usage
*****

Adds content to the ``<head>`` element. Usually used to add javascript and/or css via the ``queue_js_*`` or ``queue_css_`` family of functions.

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
        protected $_hooks = array('public_head');
    
        public function hookPublicHead($args)
        {
            queue_css_file('myplugin'); // assumes myplugin has a /views/public/css/myplugin.css file
        }    
    }


********
See Also
********

* :php:func:`queue_css_file`
* :php:func:`queue_css_string`
* :php:func:`queue_css_url`
* :php:func:`queue_js_file`
* :php:func:`queue_js_string`
* :php:func:`queue_js_url`
