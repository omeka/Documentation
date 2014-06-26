--------
Api_Item
--------

Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

.. php:class:: Api_Item

extends :php:class:`Omeka_Record_Api_AbstractRecordAdapter`

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)

        Get the REST representation of an item.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: setPostData(Omeka_Record_AbstractRecord $record, $data)

        Set POST data to an item.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:

    .. php:method:: setPutData(Omeka_Record_AbstractRecord $record, $data)

        Set PUT data to an item.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:
