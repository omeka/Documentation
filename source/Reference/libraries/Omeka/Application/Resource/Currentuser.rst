--------------------------------------
Omeka_Application_Resource_Currentuser
--------------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Currentuser

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Retrive the User record corresponding to the authenticated user.

    If the user record is not retrievable (invalid ID), then the authentication ID will be cleared.

    .. php:method:: init()

        Retrieve the User record associated with the authenticated user.

        :returns: User|null
