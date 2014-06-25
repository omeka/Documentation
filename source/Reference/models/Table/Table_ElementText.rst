-----------------
Table_ElementText
-----------------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_ElementText

extends :php:class:`Omeka_Db_Table`

    .. php:method:: getSelectForRecord($recordId, $recordType)

        :param $recordId:
        :param $recordType:
        :returns: Omeka_Db_Select

    .. php:method:: findByRecord(Omeka_Record_AbstractRecord $record)

        Find all ElementText records for a given database record (Item, File,
        etc).

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: findByElement($elementId)

        :param $elementId:
