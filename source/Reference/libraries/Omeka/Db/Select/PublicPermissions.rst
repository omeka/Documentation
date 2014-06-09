---------------------------------
Omeka_Db_Select_PublicPermissions
---------------------------------

.. php:class:: Omeka_Db_Select_PublicPermissions

    Package: :doc:`Db </Reference/packages/Db/index>`

    Encapsulates the permissions check for a record that can be public or private.

    .. php:attr:: _allPermission
    


    .. php:attr:: _selfPermission
    


    .. php:attr:: _currentUser
    


    .. php:method:: __construct(string $resource)
    
        Create the permissions object and perform the ACL checks.
        
        The permissions check relies on 'showNotPublic' and (optionally)'showSelfNotPublic' privileges on the give resource.
        
        :param string $resource: ACL resource name to check.

    .. php:method:: apply(Omeka_Db_Select $select, string $alias, string $ownerColumn = owner_id, string $publicColumn = public)
    
        Apply the permissions to an SQL select object.
        
        :param Omeka_Db_Select $select: 
        :param string $alias: Table alias to query against
        :param string $ownerColumn: Optional column for checking for ownership. If falsy, the ownership check is skipped.
        :param string $publicColumn: Optional column for storing public status. The column must represent "public" status as the value 1.