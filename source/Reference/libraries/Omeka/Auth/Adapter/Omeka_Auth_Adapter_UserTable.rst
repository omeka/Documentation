----------------------------
Omeka_Auth_Adapter_UserTable
----------------------------

Package: :doc:`Auth </Reference/packages/Auth/index>`

.. php:class:: Omeka_Auth_Adapter_UserTable

extends :php:class:`Zend_Auth_Adapter_DbTable`

    Auth adapter that uses Omeka's users table for authentication.

    .. php:method:: __construct(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db: Database object.

    .. php:method:: _authenticateValidateResult($resultIdentity)

        Validate the identity returned from the database.

        Overrides the Zend implementation to provide user IDs, not usernames upon
        successful validation.

        :type $resultIdentity: array
        :param $resultIdentity:
