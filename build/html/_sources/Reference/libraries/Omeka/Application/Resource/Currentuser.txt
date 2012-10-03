--------------------------------------
Omeka_Application_Resource_Currentuser
--------------------------------------

.. php:class:: Omeka_Application_Resource_Currentuser

    Retrive the User record corresponding to the authenticated user.
    
    If the user record is not retrievable (invalid ID), then the authentication ID will be cleared.

    .. php:method:: init()
    
        Retrieve the User record associated with the authenticated user.
        
        Note that this returns null when no User is authenticated.  Prior to 1.4, this returned boolean false.  For
        forward-compatibility, this has been changed to null in 1.4.  This is because in future versions, 
        User will implement Zend_Role_Interface.  Zend_Acl accepts null as a valid role, but it throws exceptions for
        boolean false (tries to convert it to the empty string).
        
        :returns: User|null

