--------------
Api_ElementSet
--------------

Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

.. php:class:: Api_ElementSet

extends :php:class:`Omeka_Record_Api_AbstractRecordAdapter`

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)

        Get the REST API representation for an element set.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: setPostData(Omeka_Record_AbstractRecord $record, $data)

        Set data to an ElementSet.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: ElementSet
        :param $data:
