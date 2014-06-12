

#######################
admin_navigation_global
#######################



*****
Usage
*****

Filters the global navigation of the admin theme. 

*****
Value
*****


``array`` $nav
    An array of arrays as used by Zend_Navigation. 

*********
Arguments
*********

None

********
Examples
********



The array that forms the basis for settings navigation is: 

.. code-block:: php
    
    $globalNav = array(
        array(
            'label' => __('Plugins'),
            'uri' => url('plugins'),
            'resource' => 'Plugins',
            'privilege' => 'edit'
            ),
        array(
            'label' => __('Appearance'),
            'uri' => url('appearance'),
            'resource' => 'Appearance',
            'privilege' => 'edit'
            ),
        array(
            'label' => __('Users'),
            'uri' => url('users'),
            'resource' => 'Users',
            'privilege' => 'edit'
            ),
        array(
            'label' => __('Settings'),
            'uri' => url('settings'),
            'resource' => 'Settings',
            'privilege' => 'edit'
            )
        );
        
    
To add a new link to a plugin's admin interface, you would use this filter like this:     

.. code-block:: php

    public function filterAdminNavigationGlobal($nav) 
    {
        $nav[] = array(
                        'label' => __('My Plugin'),
                        'uri' => url('my-plugin')
                      );
        return $nav;
    }
    
