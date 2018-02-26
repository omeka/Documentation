--------------------
Omeka_Test_Helper_Db
--------------------

Package: :doc:`Test\\Helper </Reference/packages/Test/Helper/index>`

.. php:class:: Omeka_Test_Helper_Db

    Catch-all class for database helper methods that are shared across test cases.

    .. php:method:: __construct(Zend_Db_Adapter_Abstract $dbAdapter, $prefix)

        :type $dbAdapter: Zend_Db_Adapter_Abstract
        :param $dbAdapter:
        :param $prefix:

    .. php:method:: __call($method, $args)

        Proxy to the db adapter object for all other requests.

        :type $method: string
        :param $method: Method name.
        :type $args: array
        :param $args: Method arguments.
        :returns: array

    .. php:method:: factory($dbConfig)

        Create an instance of the helper that is configured for the correct
        database.

        :param $dbConfig:

    .. php:method:: tableExists($tableName)

        Check whether a table exists in the database.

        :type $tableName: string
        :param $tableName:
        :returns: bool

    .. php:method:: getTableCount($prefix = null)

        Get the number of tables in the database.

        :type $prefix: string
        :param $prefix:
        :returns: int

    .. php:method:: dropTables($tables = null)

        Drop the tables from the database.

        :param $tables:

    .. php:method:: truncateTables($tables = null)

        Truncate the tables from the database.

        :param $tables:

    .. php:method:: install()

    .. php:method:: getTableNames()

        Get the tables in the database.

        :returns: array

    .. php:method:: getRowCount($tableName)

        Get the number of rows in a table.

        :type $tableName: string
        :param $tableName:
        :returns: int

    .. php:method:: getAdapter()

    .. php:method:: getPrefix()
