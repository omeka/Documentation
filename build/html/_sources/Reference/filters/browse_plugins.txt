##############
browse_plugins
##############

*****
Usage
*****

Allows you to filter the list of plugins on the admin plugins browse page

*****
Value
*****

``array`` $plugins

    Array of plugins keyed by their directory name.


*********
Arguments
*********

None


********
Examples
********

Remove plugins that do not meet minimum Omeka version unless current user is super

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('browse_plugins');
        
        public filterBrowsePlugins($plugins)
        {
            $user = current_user();
            
            if($user->getRole() != 'super') {            
                foreach($plugins as $key=>$plugin) {
                    if(!$plugin->meetsOmekaMinimumVersion()) {
                        unset($plugins[$key]);   
                    }                    
                }
            }
            return $plugins;
        }    
    }

