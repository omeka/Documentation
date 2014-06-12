#######################
public_navigation_items
#######################

*****
Usage
*****

Modifies the navigation option on public items browse page


*****
Value
*****

``array`` $navArray
    An array of arrays as used by Zend_Navigation.

*********
Arguments
*********

None

********
Examples
********

The base navigation looks like:

.. code-block:: php

        $navArray = array(
            array(
                'label' =>__('Browse All'),
                'uri' => url('items/browse'),
            ),
            array(
                'label' => __('Browse by Tag'),
                'uri' => url('items/tags')
            )
        );


So you could add to it with:

.. code-block:: php

    function filterPublicNavigationItems($navArray)
    {
        $navArray[] = array('label'=> __('My Plugin Items'),
                            'uri' => url('myplugin/items')
                            );
        return $navArray;                            
    
    }
