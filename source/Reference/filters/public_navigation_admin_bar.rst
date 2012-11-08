
###########################
public_navigation_admin_bar
###########################


*****
Usage
*****

Filters the navigation links in public theme's admin bar (the bar of links for logged-in users).

*****
Value
*****

``array`` $navLinks
    Array of navigation links
    
Begins as:

.. code-block:: php

    $navLinks = array(
        array(
            'label' => __('Welcome, %s', $user->name),
            'uri' => admin_url('/users/edit/'.$user->id)
        ),
        array(
            'label' => __('Omeka Admin'),
            'uri' => admin_url('/')
        ),
        array(
            'label' => __('Log Out'),
            'uri' => url('/users/logout')
        )
     );
     
     
*********
Arguments
*********

None

********
Examples
********

         