----------------
Table_Collection
----------------

.. php:class:: Table_Collection

    .. php:method:: applySearchFilters($select, $params)
    
        :param unknown $select: 
        :param unknown $params:

    .. php:method:: _getColumnPairs()

    .. php:method:: getSelect()
    
        Apply permissions checks to all SQL statements retrieving collections from
        the table
        
        :returns: void

    .. php:method:: findRandomFeatured()

    .. php:method:: filterByPublic($select, $isPublic)
    
        Apply a filter to the collections based on whether or not they are public
        
        :param unknown $select: 
        :param unknown $isPublic: 
        :returns: void

    .. php:method:: filterByFeatured($select, $isFeatured)
    
        Apply a filter to the collections based on whether or not they are
        featured
        
        :param unknown $select: 
        :param unknown $isFeatured: 
        :returns: void

