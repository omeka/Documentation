----------------
Table_Collection
----------------

.. php:class:: Table_Collection

    Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

    .. php:method:: applySearchFilters($select, $params)
    
        :param unknown $select: 
        :param unknown $params:

    .. php:method:: findPairsForSelectForm($options)
    
        :param unknown $options:

    .. php:method:: getSelect()
    
        Apply permissions checks to all SQL statements retrieving collections from the table
        
        :returns: void

    .. php:method:: findRandomFeatured()

    .. php:method:: applySorting(Omeka_Db_Select $select, string $sortField, string $sortDir)
    
        Enables sorting based on ElementSet,Element field strings.
        
        :param Omeka_Db_Select $select: 
        :param string $sortField: Field to sort on
        :param string $sortDir: Sorting direction (ASC or DESC)