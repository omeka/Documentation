---------------------------
Omeka_Auth_Adapter_KeyTable
---------------------------

Package: :doc:`Auth </Reference/packages/Auth/index>`

.. php:class:: Omeka_Auth_Adapter_KeyTable

implements :php:interface:`Zend_Auth_Adapter_Interface`

    Authenticate against an API key.

    .. php:attr:: _key

        protected

    .. php:method:: __construct($key = null)

        :param $key:

    .. php:method:: authenticate()

        Authenticate against an API key.

        :returns: Zend_Auth_Result|null
