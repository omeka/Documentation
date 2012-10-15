--------------------------
Omeka_Acl_Assert_Ownership
--------------------------

.. php:class:: Omeka_Acl_Assert_Ownership

    Package: Acl

    Assertion to take account of "All" and "Self" sub-permissions for records.
    
    A common use is the "edit" and "delete" permissions for Items and other"ownable" records.

    .. php:method:: assert(Zend_Acl $acl, Zend_Acl_Role_Interface $role, Zend_Acl_Resource_Interface $resource, $privilege)
    
        Assert whether or not the ACL should allow access.
        
        :param Zend_Acl $acl: 
        :param Zend_Acl_Role_Interface $role: 
        :param Zend_Acl_Resource_Interface $resource: 
        :param unknown $privilege:

    .. php:method:: _userOwnsRecord($user, $record)
    
        Check whether the user owns this specific record.
        
        :param unknown $user: 
        :param unknown $record: