-----------------------------
Omeka_Application_Resource_Db
-----------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Db

extends :php:class:`Zend_Application_Resource_Db`

    Set up the default database connection for Omeka.

    .. php:method:: init()

        :returns: Omeka_Db

    .. php:method:: setinipath($path)

        Set the path to the database configuration file.

        Allows {@link $_iniPath} to be set by the app configuration.

        :type $path: string
        :param $path:
