---------------------------------------
Omeka_Record_Api_RecordAdapterInterface
---------------------------------------

Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

.. php:interface:: Omeka_Record_Api_RecordAdapterInterface

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)

        Get the REST representation of a record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: setPostData(Omeka_Record_AbstractRecord $record, $data)

        Set data to a record during a POST request.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:

    .. php:method:: setPutData(Omeka_Record_AbstractRecord $record, $data)

        Set data to a record during a PUT request.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:
