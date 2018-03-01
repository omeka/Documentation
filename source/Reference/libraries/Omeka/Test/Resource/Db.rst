----------------------
Omeka_Test_Resource_Db
----------------------

Package: :doc:`Test\\Resource </Reference/packages/Test/Resource/index>`

.. php:class:: Omeka_Test_Resource_Db

extends :php:class:`Zend_Application_Resource_Db`

    Set up the database test environment by wiping and resetting the database to
    a recently-installed state.

    .. php:attr:: dropTables

        Flag to determine whether the tables need to be dropped. This is a slow
        process, and really should only be happening once, when the tests are
        first run.

    .. php:attr:: runInstaller

        Flag to determine whether the installer needs to be run.

    .. php:method:: init()

        Load and initialize the database.

        :returns: Omeka_Db

    .. php:method:: getDb()

        :returns: Omeka_Db

    .. php:method:: useTestConfig()

    .. php:method:: setInstall($flag)

        Set the flag that indicates whether or not to run the installer during
        init().

        :type $flag: bool
        :param $flag:

    .. php:method:: getDbAdapter()

    .. php:method:: setDbAdapter(Zend_Db_Adapter_Abstract $dbAdapter)

        :type $dbAdapter: Zend_Db_Adapter_Abstract
        :param $dbAdapter:

    .. php:method:: _getOmekaDb()

        Create a DB instance with the omeka_ prefix.

        :returns: Omeka_Db

    .. php:method:: _enableSqlLogging(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:
