---------------------
Omeka_Acl_Assert_User
---------------------

.. php:class:: Omeka_Acl_Assert_User

    Package: :doc:`Acl </Reference/packages/Acl/index>`

    Assert whether or not a specific user is allowed access to that person's user 
    account data.

    .. php:attr:: _allowSelf
    


    .. php:attr:: _denySelf
    


    .. php:method:: assert(Zend_Acl $acl, Zend_Acl_Role_Interface $role, Zend_Acl_Resource_Interface $resource, $privilege)
    
        Assert whether or not the ACL should allow access.
        
        Assertions follow this logic:
        
        Non-authenticated users (null role) have no access.
        
        There exists a set of privileges (A) that are always allowed, provided that theuser role and user resource are the same (editing own info, changing ownpassword, etc.).
        
        There also exists a set of privileges (B) that are always denied whenperformed on one's own user account (deleting own account, changing ownrole, etc.)
        
        The super user can do anything that isn't on (B), e.g. the super user account cannot modify its own role.
        
        All other users are limited to (A).
        
        :param Zend_Acl $acl: 
        :param Zend_Acl_Role_Interface $role: 
        :param Zend_Acl_Resource_Interface $resource: 
        :param unknown $privilege:

    .. php:method:: _isAllowedSelf($privilege)
    
        :param unknown $privilege:

    .. php:method:: _isDeniedSelf($privilege)
    
        :param unknown $privilege:

    .. php:method:: _isSelf($role, $resource)
    
        :param unknown $role: 
        :param unknown $resource:

    .. php:method:: _isSuperUser($user)
    
        :param unknown $user: