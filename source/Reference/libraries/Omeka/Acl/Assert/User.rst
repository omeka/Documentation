---------------------
Omeka_Acl_Assert_User
---------------------

Package: :doc:`Acl </Reference/packages/Acl/index>`

.. php:class:: Omeka_Acl_Assert_User

implements :php:interface:`Zend_Acl_Assert_Interface`

    Assert whether or not a specific user is allowed access to that person's user
    account data.

    .. php:method:: assert(Zend_Acl $acl, Zend_Acl_Role_Interface $role = null, Zend_Acl_Resource_Interface $resource = null, $privilege = null)

        Assert whether or not the ACL should allow access.

        Assertions follow this logic:

        Non-authenticated users (null role) have no access.

        There exists a set of privileges (A) that are always allowed, provided
        that the user role and user resource are the same (editing own info,
        changing own password, etc.).

        There also exists a set of privileges (B) that are always denied when
        performed on one's own user account (deleting own account, changing own
        role, etc.)

        The super user can do anything that isn't on (B), e.g. the super user
        account cannot modify its own role.

        All other users are limited to (A).

        :type $acl: Zend_Acl
        :param $acl:
        :type $role: Zend_Acl_Role_Interface
        :param $role:
        :type $resource: Zend_Acl_Resource_Interface
        :param $resource:
        :param $privilege:

    .. php:method:: _isAllowedSelf($privilege)

        :param $privilege:

    .. php:method:: _isDeniedSelf($privilege)

        :param $privilege:

    .. php:method:: _isSelf($role, $resource)

        :param $role:
        :param $resource:

    .. php:method:: _isSuperUser($user)

        :param $user:
