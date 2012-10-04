----------------------
Omeka_Test_Resource_Db
----------------------

.. php:class:: Omeka_Test_Resource_Db

    Set up the database test environment by wiping and resetting the database to
    a recently-installed state.

    .. php:attr:: _runInstaller
    


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

    .. php:method:: _truncateTables(Omeka_Db $db)
    
        Truncate all the tables in the test database.
        
        :param Omeka_Db $db: 
        :returns: void