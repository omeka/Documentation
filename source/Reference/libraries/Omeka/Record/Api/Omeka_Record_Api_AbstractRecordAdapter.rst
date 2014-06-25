--------------------------------------
Omeka_Record_Api_AbstractRecordAdapter
--------------------------------------

Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

.. php:class:: Omeka_Record_Api_AbstractRecordAdapter

implements :php:interface:`Omeka_Record_Api_RecordAdapterInterface`

    .. php:attr:: _elementsCache

        protected array

    .. php:attr:: _elementSetsCache

        protected array

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

    .. php:method:: getElementTextRepresentations(Omeka_Record_AbstractRecord $record)

        Get representations of element texts belonging to a record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: setElementTextData(Omeka_Record_AbstractRecord $record, $data)

        Set element text data to a record.

        The record must initialize the ElementText mixin.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:

    .. php:method:: getTagRepresentations(Omeka_Record_AbstractRecord $record)

        Get representations of tags belonging to a record.

        The record must initialize the Tag mixin.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: setTagData(Omeka_Record_AbstractRecord $record, $data)

        Set tag data to a record.

        The record must initialize the Tag mixin.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $data: mixed
        :param $data:

    .. php:method:: getResourceUrl($uri)

        Get the absolute URL to the passed resource.

        :type $uri: string
        :param $uri: The full resource URI
        :returns: string

    .. php:method:: getDate($date)

        Format a date string as an ISO 8601 date, UTC timezone.

        :type $date: string
        :param $date:
        :returns: string

    .. php:method:: _getUnfilteredElementTextRepresentations(Omeka_Record_AbstractRecord $record)

        Get unfiltered representations of element texts belonging to a record.

        Note the HTML flag in the representation. This indicates to the consumer
        that the representation is unfiltered.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: _getFilteredElementTextRepresentations(Omeka_Record_AbstractRecord $record)

        Get filtered representations of element texts belonging to a record.

        Note the lack of the HTML flag in the representation. This indicates to
        the consumer that the representation is filtered through the
        display_elements and array('Display',...) element texts filters.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: array

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)

        Get the REST representation of a record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
