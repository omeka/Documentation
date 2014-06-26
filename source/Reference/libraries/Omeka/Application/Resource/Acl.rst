------------------------------
Omeka_Application_Resource_Acl
------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Acl

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Initializes Omeka's ACL.

    .. php:attr:: _acl

        protected Zend_Acl

        Access control list object.

    .. php:method:: init()

        Load the hardcoded ACL definitions, then apply definitions from plugins.

        :returns: Zend_Acl

    .. php:method:: getAcl()
