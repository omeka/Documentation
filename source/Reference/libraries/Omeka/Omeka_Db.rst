--------
Omeka_Db
--------

Package: :doc:`Db </Reference/packages/Db/index>`

.. php:class:: Omeka_Db

    Database manager object for Omeka

    While mostly a wrapper for a Zend_Db_Adapter instance, this also provides shortcuts for retrieving table objects and table names for use in SQL.

    .. php:attr:: prefix

        string|null

        The prefix that every table in the omeka database will use.

    .. php:attr:: _adapter

        protected Zend_Db_Adapter_Abstract

        The database adapter.

    .. php:attr:: _tables

        protected array

        All the tables that are currently managed by this database object.

    .. php:method:: __construct($adapter, $prefix = null)

        :type $adapter: Zend_Db_Adapter_Abstract
        :param $adapter: A Zend Framework connection object.
        :type $prefix: string
        :param $prefix: The prefix for the database tables, if applicable.

    .. php:method:: __call($m, $a)

        Delegate to the database adapter.

        :type $m: string
        :param $m: Method name.
        :type $a: array
        :param $a: Method arguments.
        :returns: mixed

    .. php:method:: __get($name)

        Magic getter is a synonym for Omeka_Db::getTableName().

        Example: $db->Item is equivalent to $db->getTableName('Item').

        :type $name: string
        :param $name: Property name; table model class name in this case.
        :returns: string|null

    .. php:method:: setLogger($logger)

        Set logger for SQL queries.

        :type $logger: Zend_Log
        :param $logger:

    .. php:method:: getAdapter()

        Retrieve the database adapter.

        :returns: Zend_Db_Adapter_Abstract

    .. php:method:: getTableName($class)

        Retrieve the name of the table (including the prefix).

        :param $class:
        :returns: string

    .. php:method:: hasPrefix()

        Check whether the database tables have a prefix.

        :returns: boolean

    .. php:method:: getTable($class)

        Retrieve a table object corresponding to the model class.

        Table classes can be extended by inheriting off of Omeka_Db_Table and then
        calling your table Table_ModelName, e.g. Table_Item or Table_Collection.
        For backwards compatibility you may call your table ModelNameTable, i.e.
        ItemTable or CollectionTable. The latter naming pattern is deprecated.

        This will cache every table object so that tables are not instantiated
        multiple times for complicated web requests.

        :type $class: string
        :param $class: Model class name.
        :returns: Omeka_Db_Table

    .. php:method:: setTable($alias, Omeka_Db_Table $table)

        Cache a table object.

        Prevents the creation of unnecessary instances.

        :type $alias: string
        :param $alias:
        :type $table: Omeka_Db_Table
        :param $table:

    .. php:method:: insert($table, $values = array())

        Every query ends up looking like:
        INSERT INTO table (field, field2, field3, ...) VALUES (?, ?, ?, ...)
        ON DUPLICATE KEY UPDATE field = ?, field2 = ?, ...

        Note on portability: ON DUPLICATE KEY UPDATE is a MySQL extension.
        The advantage to using this is that it doesn't care whether a row exists
        already.
        Basically it combines what would be insert() and update() methods in other
        ORMs into a single method

        :type $table: string
        :param $table: Table model class name.
        :type $values: array
        :param $values: Rows to insert (or update).
        :returns: integer The ID for the row that got inserted (or updated).

    .. php:method:: log($sql)

        Log SQL query if logging is configured.

        This logs the query before variable substitution from bind params.

        :type $sql: string|Zend_Db_Select
        :param $sql:

    .. php:method:: queryBlock($sql, $delimiter = ';')

        Execute more than one SQL query at once.

        :type $sql: string
        :param $sql: String containing SQL queries.
        :type $delimiter: string
        :param $delimiter: Character that delimits each SQL query.

    .. php:method:: loadSqlFile($filePath)

        Read the contents of an SQL file and execute all the queries therein.

        In addition to reading the file, this will make substitutions based on
        specific naming conventions. Currently makes the following substitutions:
        %PREFIX% will be replaced by the table prefix.

        :type $filePath: string
        :param $filePath: Path to the SQL file to load
