----------------
Table_ElementSet
----------------

.. php:class:: Table_ElementSet

    .. php:method:: getSelect()

    .. php:method:: findByRecordType($recordTypeName, $includeAll = 1)
    
        Find all the element sets that correspond to a particular record type.  
        If the second param is set, this will include all element sets that belong 
        to the 'All' record type.
        
        :param unknown $recordTypeName: 
        :param unknown $includeAll: 
        :returns: array

    .. php:method:: findByName($name)
    
        :param unknown $name: