###############
admin_whitelist
###############

*****
Usage
*****

Allows admin controller views to be accessible without logging in

*****
Value
*****

``array`` $whitelist
    An array containing arrays of controller-view pairs that do not require logging in to access


*********
Arguments
*********

None



********
Examples
********

The default whitelist is:

.. code-block:: php

    array(
        array('controller' => 'users', 'action' => 'activate'),
        array('controller' => 'users', 'action' => 'login'),
        array('controller' => 'users', 'action' => 'forgot-password'),
        array('controller' => 'installer', 'action' => 'notify'),
        array('controller' => 'error', 'action' => 'error')
    );

To make your plugin's admin page accessible without login
    
.. code-block:: php

    public function filterAdminWhitelist($whitelist)
    {
        $whitelist[] = array('controller' => 'my-controller' , 'action' => 'my-view');
        return $whitelist;
    
