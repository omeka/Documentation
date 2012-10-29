--------
Omeka_Db
--------

.. php:class:: Omeka_Db

    Package: :doc:`Db </Reference/packages/Db/index>`

    Database manager object for Omeka
    
    While mostly a wrapper for a Zend_Db_Adapter instance, this also providesshortcuts for retrieving table objects and table names for use in SQL.

    .. php:attr:: prefix
    
        The prefix that every table in the omeka database will use.

    .. php:attr:: _adapter
    
        The database adapter.

    .. php:attr:: _tables
    
        All the tables that are currently managed by this database object.

    .. php:attr:: _logger
    
        The logger to use for logging SQL queries. If not set, no logging will 
        be done.

    .. php:method:: __construct(Zend_Db_Adapter_Abstract $adapter, string $prefix)
    
        :param Zend_Db_Adapter_Abstract $adapter: A Zend Framework connection object.
        :param string $prefix: The prefix for the database tables, if applicable.

    .. php:method:: __call(string $m, array $a)
    
        Delegate to the database adapter.
        
        :param string $m: Method name.
        :param array $a: Method arguments.
        :returns: mixed

    .. php:method:: __get(string $name)
    
        Magic getter is a synonym for Omeka_Db::getTableName().
        
        Example: $db->Item is equivalent to $db->getTableName('Item').
        
        :param string $name: Property name; table model class name in this case.
        :returns: string|null

    .. php:method:: setLogger(Zend_Log $logger)
    
        Set logger for SQL queries.
        
        :param Zend_Log $logger:

    .. php:method:: getAdapter()
    
        Retrieve the database adapter.
        
        :returns: Zend_Db_Adapter_Abstract

    .. php:method:: getTableName($class)
    
        Retrieve the name of the table (including the prefix).
        
        :param unknown $class: 
        :returns: string

    .. php:method:: hasPrefix()
    
        Check whether the database tables have a prefix.
        
        :returns: boolean

    .. php:method:: getTable(string $class)
    
        Retrieve a table object corresponding to the model class.
        
        Table classes can be extended by inheriting off of Omeka_Db_Table andthen calling your table Table_ModelName, e.g. Table_Item orTable_Collection. For backwards compatibility you may call your tableModelNameTable, i.e. ItemTable or CollectionTable. The latter namingpattern is deprecated.
        
        This will cache every table object so that tables are not instantiatedmultiple times for complicated web requests.
        
        :param string $class: Model class name.
        :returns: Omeka_Db_Table

    .. php:method:: setTable(string $alias, Omeka_Db_Table $table)
    
        Cache a table object.
        
        Prevents the creation of unnecessary instances.
        
        :param string $alias: 
        :param Omeka_Db_Table $table:

    .. php:method:: insert(string $table, array $values = Array)
    
        Every query ends up looking like: 
        INSERT INTO table (field, field2, field3, ...) VALUES (?, ?, ?, ...) 
        ON DUPLICATE KEY UPDATE field = ?, field2 = ?, ...
        
        Note on portability: ON DUPLICATE KEY UPDATE is a MySQL extension.The advantage to using this is that it doesn't care whether a row exists already.Basically it combines what would be insert() and update() methods in otherORMs into a single method
        
        :param string $table: Table model class name.
        :param array $values: Rows to insert (or update).
        :returns: integer The ID for the row that got inserted (or updated).

    .. php:method:: log(string|Zend_Db_Select $sql)
    
        Log SQL query if logging is configured.
        
        This logs the query before variable substitution from bind params.
        
        :param string|Zend_Db_Select $sql:

    .. php:method:: queryBlock(string $sql, string $delimiter = ;)
    
        Execute more than one SQL query at once.
        
        :param string $sql: String containing SQL queries.
        :param string $delimiter: Character that delimits each SQL query.

    .. php:method:: loadSqlFile(string $filePath)
    
        Read the contents of an SQL file and execute all the queries therein.
        
        In addition to reading the file, this will make substitutions based onspecific naming conventions. Currently makes the following substitutions:%PREFIX% will be replaced by the table prefix.
        
        :param string $filePath: Path to the SQL file to load