----------------------------------
Omeka_Controller_Action_Helper_Acl
----------------------------------

.. php:class:: Omeka_Controller_Action_Helper_Acl

    Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

    Leverages the ACL to automatically check permissions for the current
    controller/action combo.

    .. php:attr:: _acl
    
        ACL object.

    .. php:attr:: _currentUser
    
        User record corresponding to the logged-in user, otherwise null.

    .. php:attr:: _allowed
    
        Temporarily allowed permissions.

    .. php:attr:: _autoloadResourceObject
    
        Whether we should automatically try to set the resource object.

    .. php:method:: __construct(Zend_Acl $acl, $currentUser)
    
        Instantiated with the ACL permissions which will be used to verify
        permission levels.
        
        :param Zend_Acl $acl: 
        :param unknown $currentUser:

    .. php:method:: preDispatch()
    
        Determine whether or not access is granted to a specific controller/action.
        
        If the user has been authenticated, display the Access Forbidden error page.Otherwise, give the user an opportunity to login before trying again.
        
        :returns: void

    .. php:method:: isAllowed(string $privilege, $resource)
    
        Notifies whether the logged-in user has permission for a given resource/
        privilege combination.
        
        If an ACL resource being checked has not been defined, access to thatresource should not be controlled.  This allows plugin writers toimplement controllers without also requiring them to be aware of the ACL.
        
        Conversely, in the event that an ACL resource has been defined, all access permissions for that controller must be properly defined.
        
        The names of resources should correspond to the name of the controllerclass minus 'Controller', e.g.Geolocation_IndexController -> 'Geolocation_Index'CollectionsController -> 'Collections'
        
        :param string $privilege: 
        :param unknown $resource: 
        :returns: boolean

    .. php:method:: getResourceName()
    
        Retrieve the name of the ACL resource based on the name of the controller
        and, if not the default module, the name of the module.
        
        :returns: string

    .. php:method:: setCurrentUser(User|null $currentUser)
    
        :param User|null $currentUser:

    .. php:method:: setAllowed(string $rule, boolean $isAllowed = 1)
    
        Temporarily override the ACL's permissions for this controller
        
        :param string $rule: 
        :param boolean $isAllowed:

    .. php:method:: setAutoloadResourceObject(boolean $autoload)
    
        Set whether the ACL helper should try to automatically load
        a resource object from the request.
        
        :param boolean $autoload:

    .. php:method:: _getResourceObjectFromRequest()
    
        Try to get the current resource object for the request.
        
        :returns: Zend_Acl_Resource_Interface|null

    .. php:method:: _isLoginRequest()