----------
Table_Item
----------

.. php:class:: Table_Item

    Package: :doc:`/Reference/packages/Db\Table/index`

    .. php:method:: filterByRange(Omeka_Db_Select $select, string $range)
    
        Can specify a range of valid Item IDs or an individual ID
        
        :param Omeka_Db_Select $select: 
        :param string $range: Example: 1-4, 75, 89
        :returns: void

    .. php:method:: filterBySearch($select, $params)
    
        Run the search filter on the SELECT statement
        
        :param unknown $select: 
        :param unknown $params: 
        :returns: void

    .. php:method:: _simpleSearch(Zend_Db_Select $select, $terms)
    
        Build the simple search.
        
        The search query consists of a derived table that is INNER JOINed to themain SQL query.  That derived table is a
        union of two SELECT queries. Thefirst query searches the FULLTEXT index on the items_elements table, andthe second
        query searches the tags table for every word in the searchterms and assigns each found result a rank of '1'. That
        should maketagged items show up higher on the found results list for a given search.
        
        :param Zend_Db_Select $select: 
        :param unknown $terms:

    .. php:method:: _advancedSearch(Zend_Db_Select $select, $terms)
    
        Build the advanced search.
        
        :param Zend_Db_Select $select: 
        :param unknown $terms:

    .. php:method:: filterByPublic($select, $isPublic)
    
        Apply a filter to the items based on whether or not they should be public
        
        :param unknown $select: 
        :param unknown $isPublic: 
        :returns: void

    .. php:method:: filterByFeatured($select, $isFeatured)
    
        :param unknown $select: 
        :param unknown $isFeatured:

    .. php:method:: filterByCollection($select, $collection)
    
        Filter the SELECT statement based on an item's collection
        
        :param unknown $select: 
        :param unknown $collection: 
        :returns: void

    .. php:method:: filterByItemType($select, $type)
    
        Filter the SELECT statement based on the item Type
        
        :param unknown $select: 
        :param unknown $type: 
        :returns: void

    .. php:method:: filterByTags($select, $tags)
    
        Query must look like the following in order to correctly retrieve items
        that have all the tags provided (in this example, all items that are
        tagged both 'foo' and 'bar'):
        
        SELECT i.idFROM omeka_items iWHERE(i.id IN(SELECT tg.record_id as idFROM omeka_records_tags tgINNER JOIN omeka_tags
        t ON t.id = tg.tag_idWHERE t.name = 'foo' AND tg.record_type = 'Item')AND i.id IN(SELECT tg.record_id as idFROM
        omeka_records_tags tgINNER JOIN omeka_tags t ON t.id = tg.tag_idWHERE t.name = 'bar' AND tg.record_type =
        'Item'))...
        
        :param unknown $select: 
        :param unknown $tags: 
        :returns: void

    .. php:method:: filterByUser($select, integer $userId, $isUser = 1)
    
        Filter the SELECT based on the user who owns the item
        
        :param unknown $select: 
        :param integer $userId:  ID of the User to filter by
        :param unknown $isUser: 
        :returns: void

    .. php:method:: filterByExcludedTags($select, $tags)
    
        Filter SELECT statement based on items that are not tagged with a specific
        set of tags
        
        :param unknown $select: 
        :param unknown $tags: 
        :returns: void

    .. php:method:: filterByHasDerivativeImage($select, boolean $hasDerivativeImage = 1)
    
        Filter SELECT statement based on whether items have a derivative image
        file.
        
        :param unknown $select: 
        :param boolean $hasDerivativeImage: Whether items should have a derivative image file.
        :returns: void

    .. php:method:: applySearchFilters($select, $params)
    
        Possible options: 'public','user','featured','collection','type','tag',
        'excludeTags', 'search', 'range', 'advanced', 'hasImage',
        
        :param unknown $select: 
        :param unknown $params: 
        :returns: void

    .. php:method:: applySorting(Omeka_Db_Select $select, string $sortField, string $sortDir)
    
        Enables sorting based on ElementSet,Element field strings.
        
        :param Omeka_Db_Select $select: 
        :param string $sortField: Field to sort on
        :param string $sortDir: Sorting direction (ASC or DESC)

    .. php:method:: getSelect()
    
        This is a kind of simple factory that spits out proper beginnings
        of SQL statements when retrieving items
        
        :returns: Omeka_Db_Select

    .. php:method:: findFirst()
    
        Return the first item accessible to the current user.
        
        :returns: Item|null

    .. php:method:: findLast()
    
        Return the last item accessible to the current user.
        
        :returns: Item|null

    .. php:method:: findPrevious($item)
    
        :param unknown $item:

    .. php:method:: findNext($item)
    
        :param unknown $item:

    .. php:method:: findNearby($item, $position = next)
    
        :param unknown $item: 
        :param unknown $position: