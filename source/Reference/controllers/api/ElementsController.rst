------------------
ElementsController
------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: ElementsController

extends :php:class:`ApiController`

    The controller for API /elements.

    .. php:method:: deleteAction()

        Handle DELETE requests.

    .. php:method:: init()

        Initialize this controller.

    .. php:method:: indexAction()

        Handle GET request without ID.

    .. php:method:: getAction()

        Handle GET request with ID.

    .. php:method:: postAction()

        Handle POST requests.

    .. php:method:: putAction()

        Handle PUT requests.

    .. php:method:: _validateRecordType($recordType)

        Validate a record type.

        :type $recordType: string
        :param $recordType:

    .. php:method:: _validateUser(Omeka_Record_AbstractRecord $record, $privilege)

        Validate a user against a privilege.

        For GET requests, assume that records without an ACL resource do not
        require a permission check. Note that for POST, PUT, and DELETE, all
        records must define an ACL resource.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $privilege: string
        :param $privilege:

    .. php:method:: _getRecordAdapter($recordType)

        Get the adapter for a record type.

        :type $recordType: string
        :param $recordType:
        :returns: Omeka_Record_Api_AbstractRecordAdapter

    .. php:method:: _setLinkHeader($perPage, $page, $totalResults, $resource)

        Set the Link header for pagination.

        :type $perPage: int
        :param $perPage:
        :type $page: int
        :param $page:
        :type $totalResults: int
        :param $totalResults:
        :type $resource: string
        :param $resource:

    .. php:method:: _getRepresentation(Omeka_Record_Api_AbstractRecordAdapter $recordAdapter, Omeka_Record_AbstractRecord $record, $resource)

        Get the representation of a record.

        :type $recordAdapter: Omeka_Record_Api_AbstractRecordAdapter
        :param $recordAdapter:
        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $resource: string
        :param $resource:
