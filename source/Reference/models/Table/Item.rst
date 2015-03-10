----------
Table_Item
----------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_Item

extends :php:class:`Omeka_Db_Table`

    .. php:method:: filterBySearch($select, $params)

        Run the search filter on the SELECT statement

        :param $select:
        :param $params:
        :returns: void

    .. php:method:: _simpleSearch($select, $terms)

        Build the simple search.

        The search query consists of a derived table that is INNER JOINed to the
        main SQL query.  That derived table is a union of two SELECT queries. The
        first query searches the FULLTEXT index on the items_elements table, and
        the second query searches the tags table for every word in the search
        terms and assigns each found result a rank of '1'. That should make tagged
        items show up higher on the found results list for a given search.

        :type $select: Zend_Db_Select
        :param $select:
        :param $terms:

    .. php:method:: _advancedSearch($select, $terms)

        Build the advanced search.

        :type $select: Zend_Db_Select
        :param $select:
        :param $terms:

    .. php:method:: filterByCollection($select, $collection)

        Filter the SELECT statement based on an item's collection

        :param $select:
        :param $collection:
        :returns: void

    .. php:method:: filterByItemType($select, $type)

        Filter the SELECT statement based on the item Type

        :param $select:
        :param $type:
        :returns: void

    .. php:method:: filterByTags($select, $tags)

        Query must look like the following in order to correctly retrieve items
        that have all the tags provided (in this example, all items that are
        tagged both 'foo' and 'bar'):

        SELECT i.id FROM omeka_items i WHERE
        (
        i.id IN
        (SELECT tg.record_id as id FROM omeka_records_tags tg INNER JOIN
        omeka_tags t ON t.id = tg.tag_id WHERE t.name = 'foo' AND tg.record_type =
        'Item')
        AND i.id IN
        (SELECT tg.record_id as id FROM omeka_records_tags tg INNER JOIN
        omeka_tags t ON t.id = tg.tag_id WHERE t.name = 'bar' AND tg.record_type =
        'Item')
        )
        ...

        :param $select:
        :param $tags:
        :returns: void

    .. php:method:: filterByExcludedTags($select, $tags)

        Filter SELECT statement based on items that are not tagged with a specific
        set of tags

        :param $select:
        :param $tags:
        :returns: void

    .. php:method:: filterByHasDerivativeImage($select, $hasDerivativeImage = true)

        Filter SELECT statement based on whether items have a derivative image
        file.

        :param $select:
        :type $hasDerivativeImage: boolean
        :param $hasDerivativeImage: Whether items should have a derivative image file.
        :returns: void

    .. php:method:: applySearchFilters($select, $params)

        :param $select:
        :param $params:
        :returns: void

    .. php:method:: applySorting($select, $sortField, $sortDir)

        Enables sorting based on ElementSet,Element field strings.

        :type $select: Omeka_Db_Select
        :param $select:
        :type $sortField: string
        :param $sortField: Field to sort on
        :type $sortDir: string
        :param $sortDir: Sorting direction (ASC or DESC)

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

        :param $item:

    .. php:method:: findNext($item)

        :param $item:

    .. php:method:: findNearby($item, $position = 'next')

        :param $item:
        :param $position:
