######################
public_navigation_main
######################

*****
Usage
*****

Modifies the top-level navigation for the public theme. 

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


    
To add a new link to a plugin's public interface, you would use this filter like this:     

.. code-block:: php

    public function filterPublicNavigationMain($nav) 
    {
        $nav[] = array(
                        'label' => __('My Plugin'),
                        'uri' => url('my-plugin')
                      );
        return $nav;
    }
    
    