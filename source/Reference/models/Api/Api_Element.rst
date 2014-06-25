-----------
Api_Element
-----------

Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

.. php:class:: Api_Element

extends :php:class:`Omeka_Record_Api_AbstractRecordAdapter`

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)

        Get the REST API representation for an element.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: setPostData(Omeka_Record_AbstractRecord $record, $data)

        Set POST data to an Element.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: Element
        :param $data:

    .. php:method:: setPutData(Omeka_Record_AbstractRecord $record, $data)

        Set PUT data to an Element.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: Element
        :param $data:
