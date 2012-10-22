#########################
admin_navigation_settings
#########################

*****
Usage
*****

Filters the navigation for the settings page of the admin theme. 

*********
Arguments
*********


``array`` $nav

    An array of arrays as used by Zend_Navigation.

********
Examples
********



The array that forms the basis for settings navigation is: 

.. code-block:: php
    
    $navArray = array(
        array(
            'label' => __('General Settings'),
            'uri' => url('settings')
        ),
        array(
            'label' => __('Element Sets'),
            'uri' => url('element-sets'),
            'resource' => 'ElementSets',
            'privilege' => 'browse'
        ),
        array(
            'label' => __('Security Settings'),
            'uri' => url('security'),
            'resource' => 'Security',
            'privilege' => 'edit'
        ),
        array(
            'label' => __('Search Settings'),
            'uri' => url('search/settings')
        )
    );
        
    
To add a new link to a plugin's admin interface, you would use this filter like this:     

.. code-block:: php

    public function filterAdminNavigationSettings($nav) 
    {
        $nav[] = array(
                        'label' => __('My Plugin Settings'),
                        'uri' => url('my-plugin/settings')
                      );
        return $nav;
    }
    