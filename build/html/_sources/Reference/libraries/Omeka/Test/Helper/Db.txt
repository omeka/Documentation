--------------------
Omeka_Test_Helper_Db
--------------------

.. php:class:: Omeka_Test_Helper_Db

    Catch-all class for database helper methods that are shared across test cases.

    .. php:attr:: _dbAdapter
    
        Database adapter object.

    .. php:method:: __construct(Zend_Db_Adapter_Abstract $dbAdapter)
    
        :param Zend_Db_Adapter_Abstract $dbAdapter:

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

    .. php:method:: truncateTables($prefix)
    
        Truncate all of the tables in the test database.
        
        :param unknown $prefix: 
        :returns: void

    .. php:method:: loadDbSchema(string $pathToSchemaFile, string $tablePrefix = omeka_)
    
        Initialize the database schema.
        
        :param string $pathToSchemaFile: 
        :param string $tablePrefix: 
        :returns: void

    .. php:method:: loadXmlSchema(string $xmlFile, string $schemaName, boolean $flat = )
    
        Set up one or more database tables according to the given XML file,
        which follows the structure of PHPUnit's XmlDataSet (or FlatXmlDataSet).
        
        :param string $xmlFile: Path to XML file.
        :param string $schemaName: Name of database schema for which to load the XML file.
        :param boolean $flat: Whether or not the file is in PHPUnit's Flat XML format.

    .. php:method:: dropTables(string $prefix)
    
        Drop the tables from the database.
        
        :param string $prefix: Optionally, delete only tables with this prefix.
        :returns: void

    .. php:method:: getTableNames(string $prefix)
    
        Get the tables in the database.
        
        :param string $prefix: Optionally, show only tables with this prefix.
        :returns: array

    .. php:method:: getRowCount(string $tableName)
    
        Get the number of rows in a table.
        
        :param string $tableName: 
        :returns: integer

    .. php:method:: getAdapter()