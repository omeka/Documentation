---------------------------------
Omeka_Db_Select_PublicPermissions
---------------------------------

Package: :doc:`Db </Reference/packages/Db/index>`

.. php:class:: Omeka_Db_Select_PublicPermissions

    Encapsulates the permissions check for a record that can be public or private.

    .. php:attr:: _allPermission

        protected

    .. php:attr:: _selfPermission

        protected

    .. php:attr:: _currentUser

        protected

    .. php:method:: __construct($resource)

        Create the permissions object and perform the ACL checks.

        The permissions check relies on 'showNotPublic' and (optionally)
        'showSelfNotPublic' privileges on the give resource.

        :type $resource: string
        :param $resource: ACL resource name to check.

    .. php:method:: apply(Omeka_Db_Select $select, $alias, $ownerColumn = 'owner_id', $publicColumn = 'public')

        Apply the permissions to an SQL select object.

        :type $select: Omeka_Db_Select
        :param $select:
        :type $alias: string
        :param $alias: Table alias to query against
        :type $ownerColumn: string
        :param $ownerColumn: Optional column for checking for ownership. If falsy, the ownership check is skipped.
        :type $publicColumn: string
        :param $publicColumn: Optional column for storing public status. The column must represent "public" status as the value 1.
