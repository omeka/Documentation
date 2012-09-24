----------------
Table_SearchText
----------------

.. php:class:: Table_SearchText

    .. php:method:: findByRecord(string $recordType, int $recordId)
    
        Find search text by record.
        
        :param string $recordType: 
        :param int $recordId: 
        :returns: SearchText|null

    .. php:method:: search(string $query, string $recordType)
    
        Perform a fulltext search.
        
        :param string $query: 
        :param string $recordType: Limit results to this record type.
        :returns: array

