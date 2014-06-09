---------------------
ElementSetsController
---------------------

.. php:class:: ElementSetsController

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    The controller for API /element_sets.

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

    .. php:method:: _validateRecordType(string $recordType)
    
        Validate a record type.
        
        :param string $recordType:

    .. php:method:: _validateUser(Omeka_Record_AbstractRecord $record, string $privilege)
    
        Validate a user against a privilege.
        
        For GET requests, assume that records without an ACL resource do notrequire a permission check. Note that for POST, PUT, and DELETE, allrecords must define an ACL resource.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param string $privilege:

    .. php:method:: _getRecordAdapter(string $recordType)
    
        Get the adapter for a record type.
        
        :param string $recordType: 
        :returns: Omeka_Record_Api_AbstractRecordAdapter

    .. php:method:: _setLinkHeader(int $perPage, int $page, int $totalResults, string $resource)
    
        Set the Link header for pagination.
        
        :param int $perPage: 
        :param int $page: 
        :param int $totalResults: 
        :param string $resource:

    .. php:method:: _getRepresentation(Omeka_Record_Api_AbstractRecordAdapter $recordAdapter, Omeka_Record_AbstractRecord $record, string $resource)
    
        Get the representation of a record.
        
        :param Omeka_Record_Api_AbstractRecordAdapter $recordAdapter: 
        :param Omeka_Record_AbstractRecord $record: 
        :param string $resource: