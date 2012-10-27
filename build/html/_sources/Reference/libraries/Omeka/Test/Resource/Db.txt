----------------------
Omeka_Test_Resource_Db
----------------------

.. php:class:: Omeka_Test_Resource_Db

    Package: :doc:`Test\\Resource </Reference/packages/Test/Resource/index>`

    Set up the database test environment by wiping and resetting the database to
    a recently-installed state.

    .. php:attr:: dropTables
    
        Flag to determine whether the tables need to be dropped. This is a slow
        process, and really should only be happening once, when the tests are
        first run.

    .. php:attr:: runInstaller
    
        Flag to determine whether the installer needs to be run.

    .. php:attr:: _cachedAdapter
    
        Avoid issues with database connections not closing properly after each 
        test run.

    .. php:method:: init()
    
        Load and initialize the database.
        
        :returns: Omeka_Db

    .. php:method:: getDb()
    
        :returns: Omeka_Db

    .. php:method:: useTestConfig()

    .. php:method:: setInstall(boolean $flag)
    
        Set the flag that indicates whether or not to run the installer during 
        init().
        
        :param boolean $flag:

    .. php:method:: getDbAdapter()

    .. php:method:: setDbAdapter(Zend_Db_Adapter_Abstract $dbAdapter)
    
        :param Zend_Db_Adapter_Abstract $dbAdapter:

    .. php:method:: _getOmekaDb()
    
        Create a DB instance with the omeka_ prefix.
        
        :returns: Omeka_Db

    .. php:method:: _enableSqlLogging(Omeka_Db $db)
    
        :param Omeka_Db $db: