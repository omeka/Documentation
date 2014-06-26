---------------------
Installer_Task_Schema
---------------------

Package: :doc:`Install </Reference/packages/Install/index>`

.. php:class:: Installer_Task_Schema

implements :php:interface:`Installer_TaskInterface`

    Load the database schema for an Omeka installation.

    Schema should be defined in an SQL file.

    .. php:method:: addTable($tableName, $sqlFilePath)

        Add an SQL table to the list of tables to create.

        :type $tableName: string
        :param $tableName:
        :type $sqlFilePath: string
        :param $sqlFilePath:

    .. php:method:: addTables($tables)

        Add a set of SQL tables to the list.

        :type $tables: array
        :param $tables:

    .. php:method:: setTables($tables)

        Set the list of SQL tables.

        :type $tables: array
        :param $tables:

    .. php:method:: removeTable($tableName)

        Remove an SQL table from the list.

        :type $tableName: string
        :param $tableName:

    .. php:method:: getTables()

        Retrieve list of tables being installed.

    .. php:method:: useDefaultTables()

        Add all tables corresponding to the default Omeka installation.

    .. php:method:: install(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:
