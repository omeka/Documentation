###########################
admin_navigation_appearance
###########################

.. versionadded:: 2.5.1

*****
Usage
*****

Filters the navigation for the appearance settings pages of the admin theme. 

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

The array that forms the basis for the appearance navigation is: 

.. code-block:: php

    $navArray = array(
        array(
            'label' => __('Themes'),
            'uri' => url('themes'),
            'resource' => 'Themes',
            'privilege' => 'edit'
        ),
        array(
            'label' => __('Navigation'),
            'uri' => url('appearance/edit-navigation')
        ),
        array(
            'label' => __('Settings'),
            'uri' => url('appearance/edit-settings')
        ),
    );
        
    
To add a new link to the appearance nav, you would use this filter like this:     

.. code-block:: php

    public function filterAdminNavigationAppearance($nav) 
    {
        $nav[] = array(
            'label' => __('My Plugin Settings'),
            'uri' => url('my-plugin/settings')
        );
        return $nav;
    }
    
