---------
Table_Tag
---------

.. php:class:: Table_Tag

    .. php:method:: findOrNew($name)
    
        :param unknown $name:

    .. php:method:: filterByRecord($select, $record)
    
        Filter a SELECT statement based on an Omeka_Record_AbstractRecord instance
        
        :param unknown $select: 
        :param unknown $record: 
        :returns: void

    .. php:method:: applySorting(Omeka_Db_Select $select, string $sortField, string $sortDir)
    
        Apply custom sorting for tags.
        
        This also applies the normal, built-in sorting.
        
        :param Omeka_Db_Select $select: 
        :param string $sortField: Sorting field.
        :param string $sortDir: Sorting direction, suitable for direct inclusion in SQL (ASC or DESC).

    .. php:method:: filterByTagType($select, $type)
    
        Filter SELECT statement based on the type of tags to view (Item, Exhibit, etc.)
        
        :param unknown $select: 
        :param unknown $type: 
        :returns: void

    .. php:method:: filterByTagNameLike($select, $partialTagName)
    
        Filter SELECT statement based on whether the tag contains the partial tag name
        
        :param unknown $select: 
        :param unknown $partialTagName: 
        :returns: void

    .. php:method:: applySearchFilters($select, array $params = Array)
    
        Retrieve a certain number of tags
        
        :param unknown $select: 
        :param array $params: 'limit' => integer 'record' => instanceof Omeka_Record_AbstractRecord 'like' => partial_tag_name 'type' => tag_type
        :returns: void

    .. php:method:: getSelect()
    
        :returns: Omeka_Db_Select

    .. php:method:: findTagNamesLike($partialName, $limit = 10)
    
        :param unknown $partialName: 
        :param unknown $limit:

