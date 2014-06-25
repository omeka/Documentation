--------------------------
Omeka_Acl_Assert_Ownership
--------------------------

Package: :doc:`Acl </Reference/packages/Acl/index>`

.. php:class:: Omeka_Acl_Assert_Ownership

implements :php:interface:`Zend_Acl_Assert_Interface`

    Assertion to take account of "All" and "Self" sub-permissions for records.

    A common use is the "edit" and "delete" permissions for Items and other
    "ownable" records.

    .. php:method:: assert(Zend_Acl $acl, Zend_Acl_Role_Interface $role = null, Zend_Acl_Resource_Interface $resource = null, $privilege = null)

        Assert whether or not the ACL should allow access.

        :type $acl: Zend_Acl
        :param $acl:
        :type $role: Zend_Acl_Role_Interface
        :param $role:
        :type $resource: Zend_Acl_Resource_Interface
        :param $resource:
        :param $privilege:

    .. php:method:: _userOwnsRecord($user, $record)

        Check whether the user owns this specific record.

        :param $user:
        :param $record:
