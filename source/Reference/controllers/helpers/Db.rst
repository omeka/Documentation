---------------------------------
Omeka_Controller_Action_Helper_Db
---------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_Db

extends :php:class:`Zend_Controller_Action_Helper_Abstract`

    An action helper replacement for the database-oriented methods that were
    baked into Omeka_Controller_AbstractActionController in v1.x.

    .. php:method:: __construct(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: init()

    .. php:method:: __call($method, $args)

        Delegate to the default table object for all other method calls.

        :param $method:
        :param $args:

    .. php:method:: setDefaultModelName($modelName)

        Set the class name corresponding to the default model.

        :param $modelName:

    .. php:method:: getDefaultModelName()

    .. php:method:: setDefaultTable(Omeka_Db_Table $table)

        :type $table: Omeka_Db_Table
        :param $table:

    .. php:method:: getDb()

    .. php:method:: getTable($tableName = null)

        :type $tableName: string|null
        :param $tableName:
        :returns: Omeka_Db_Table

    .. php:method:: findById($id = null, $table = null)

        Find a particular record given its unique ID # and (optionally) its class
        name.

        :param $id:
        :param $table:
        :returns: Omeka_Record_AbstractRecord
