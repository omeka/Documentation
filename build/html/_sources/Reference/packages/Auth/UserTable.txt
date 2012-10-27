----------------------------
Omeka_Auth_Adapter_UserTable
----------------------------

.. php:class:: Omeka_Auth_Adapter_UserTable

    Package: :doc:`Auth </Reference/packages/Auth/index>`

    Auth adapter that uses Omeka's users table for authentication.

    .. php:method:: __construct(Omeka_Db $db)
    
        :param Omeka_Db $db: Database object.

    .. php:method:: _authenticateValidateResult(array $resultIdentity)
    
        Validate the identity returned from the database.
        
        Overrides the Zend implementation to provide user IDs, not usernamesupon successful validation.
        
        :param array $resultIdentity: