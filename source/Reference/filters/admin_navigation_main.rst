#####################
admin_navigation_main
#####################

*****
Usage
*****

Modifies the top-level navigation for the admin theme. 

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

The array that forms the basis for admin navigation is: 

.. code-block:: php
    
        $mainNav = array(
            array(
                'label' => __('Dashboard'),
                'uri' => url('')
            ),
            array(
                'label' => __('Items'),
                'uri' => url('items')
            ),
            array(
                'label' => __('Collections'),
                'uri' => url('collections')
            ),
            array(
                'label' => __('Item Types'),
                'uri' => url('item-types')
            ),
            array(
                'label' => __('Tags'),
                'uri' => url('tags')
            )
        );
        
    
To add a new link to a plugin's admin interface, you would use this filter like this:     

.. code-block:: php

    public function filterAdminNavigationMain($nav) 
    {
        $nav[] = array(
                        'label' => __('My Plugin'),
                        'uri' => url('my-plugin')
                      );
        return $nav;
    }
    
    
