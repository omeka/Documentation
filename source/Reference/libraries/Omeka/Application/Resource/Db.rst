-----------------------------
Omeka_Application_Resource_Db
-----------------------------

.. php:class:: Omeka_Application_Resource_Db

    Package: :doc:`/Reference/packages/Application\Resource/index`

    Set up the default database connection for Omeka.

    .. php:attr:: _iniPath
    
        Path to the database configuration file.
        Set in application.ini

    .. php:method:: init()
    
        :returns: Omeka_Db

    .. php:method:: setinipath(string $path)
    
        Set the path to the database configuration file.
        
        Allows {@link $_iniPath} to be set by the app configuration.
        
        :param string $path: