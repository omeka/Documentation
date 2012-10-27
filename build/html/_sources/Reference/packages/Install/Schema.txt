---------------------
Installer_Task_Schema
---------------------

.. php:class:: Installer_Task_Schema

    Package: :doc:`Install </Reference/packages/Install/index>`

    Load the database schema for an Omeka installation.
    
    Schema should be defined in an SQL file.

    .. php:attr:: _defaultTables
    


    .. php:attr:: _tables
    


    .. php:method:: addTable(string $tableName, string $sqlFilePath)
    
        Add an SQL table to the list of tables to create.
        
        :param string $tableName: 
        :param string $sqlFilePath:

    .. php:method:: addTables(array $tables)
    
        Add a set of SQL tables to the list.
        
        :param array $tables:

    .. php:method:: setTables(array $tables)
    
        Set the list of SQL tables.
        
        :param array $tables:

    .. php:method:: removeTable(string $tableName)
    
        Remove an SQL table from the list.
        
        :param string $tableName:

    .. php:method:: getTables()
    
        Retrieve list of tables being installed.

    .. php:method:: useDefaultTables()
    
        Add all tables corresponding to the default Omeka installation.

    .. php:method:: install(Omeka_Db $db)
    
        :param Omeka_Db $db: