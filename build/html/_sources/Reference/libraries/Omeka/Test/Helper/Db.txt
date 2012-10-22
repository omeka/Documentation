--------------------
Omeka_Test_Helper_Db
--------------------

.. php:class:: Omeka_Test_Helper_Db

    Package: :doc:`/Reference/packages/Test\Helper/index`

    Catch-all class for database helper methods that are shared across test cases.

    .. php:attr:: _dbAdapter
    
        Database adapter object.

    .. php:attr:: _prefix
    


    .. php:method:: __construct(Zend_Db_Adapter_Abstract $dbAdapter, $prefix)
    
        :param Zend_Db_Adapter_Abstract $dbAdapter: 
        :param unknown $prefix:

    .. php:method:: __call(string $method, array $args)
    
        Proxy to the db adapter object for all other requests.
        
        :param string $method: Method name.
        :param array $args: Method arguments.
        :returns: array

    .. php:method:: factory($dbConfig)
    
        Create an instance of the helper that is configured for the correct 
        database.
        
        :param unknown $dbConfig:

    .. php:method:: tableExists(string $tableName)
    
        Check whether a table exists in the database.
        
        :param string $tableName: 
        :returns: boolean

    .. php:method:: getTableCount(string $prefix)
    
        Get the number of tables in the database.
        
        :param string $prefix: 
        :returns: integer

    .. php:method:: dropTables($tables)
    
        Drop the tables from the database.
        
        :param unknown $tables: 
        :returns: void

    .. php:method:: truncateTables($tables)
    
        Truncate the tables from the database.
        
        :param unknown $tables: 
        :returns: void

    .. php:method:: install()

    .. php:method:: getTableNames()
    
        Get the tables in the database.
        
        :returns: array

    .. php:method:: getRowCount(string $tableName)
    
        Get the number of rows in a table.
        
        :param string $tableName: 
        :returns: integer

    .. php:method:: getAdapter()

    .. php:method:: getPrefix()