------------------------------
Omeka_Application_Resource_Acl
------------------------------

.. php:class:: Omeka_Application_Resource_Acl

    Package: :doc:`/Reference/packages/Application\Resource/index`

    Initializes Omeka's ACL.

    .. php:attr:: _acl
    
        Access control list object.

    .. php:method:: init()
    
        Load the hardcoded ACL definitions, then apply definitions from plugins.
        
        :returns: Zend_Acl

    .. php:method:: getAcl()