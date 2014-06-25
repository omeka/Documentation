---------------
Mixin_Timestamp
---------------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_Timestamp

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    Mixin for models that keep added and/or modified timestamps.

    .. php:attr:: _record

        protected

    .. php:attr:: _addedColumn

        protected

    .. php:attr:: _modifiedColumn

        protected

    .. php:method:: __construct($record, $addedColumn = 'added', $modifiedColumn = 'modified')

        Initialize the mixin.

        Setting either of the column parameters to null will skip updating that
        timestamp. The default column names are 'updated' and 'added'.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $addedColumn: string
        :param $addedColumn: Name of the column holding the "added" timestamp.
        :param $modifiedColumn:

    .. php:method:: beforeSave($args)

        Before saving a record, set the "updated" timestamp.

        :param $args:

    .. php:method:: _setTimestamp($column)

        Update a timestamp column for the underlying record.

        :type $column: string
        :param $column: Column to update.
