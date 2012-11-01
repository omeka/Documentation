#############
define_routes
#############

*****
Usage
*****

This hook allows the plugin writer to add routes to Omeka.

Routes can be used to create custom URLs that are different than the default ones provided by Omeka for plugin pages. 

*********
Arguments
*********

``Zend_Controller_Router_Rewrite`` router

********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('define_routes');
                
        function hookDefineRoutes($args)
        {
            // Don't add these routes on the admin side to avoid conflicts.
            if (is_admin_theme()) {
                return;
            }
    
            $router = $args['router'];
    
            // Add custom routes based on the page slug.
            $pages = get_db()->getTable('SimplePagesPage')->findAll();
            foreach ($pages as $page) {
                $router->addRoute(
                    'simple_pages_show_page_' . $page->id, 
                    new Zend_Controller_Router_Route(
                        $page->slug, 
                        array(
                            'module'       => 'simple-pages', 
                            'controller'   => 'page', 
                            'action'       => 'show', 
                            'id'           => $page->id
                        )
                    )
                );
            }
        }       

    }
    
    
********
See Also
********

:ref:`understanding_routes`    