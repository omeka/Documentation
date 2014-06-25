----------------
Table_Collection
----------------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_Collection

extends :php:class:`Omeka_Db_Table`

    .. php:method:: applySearchFilters($select, $params)

        :param $select:
        :param $params:

    .. php:method:: findPairsForSelectForm($options = array())

        :param $options:

    .. php:method:: getSelect()

        Apply permissions checks to all SQL statements retrieving collections from
        the table

        :returns: void

    .. php:method:: findRandomFeatured()

    .. php:method:: applySorting($select, $sortField, $sortDir)

        Enables sorting based on ElementSet,Element field strings.

        :type $select: Omeka_Db_Select
        :param $select:
        :type $sortField: string
        :param $sortField: Field to sort on
        :type $sortDir: string
        :param $sortDir: Sorting direction (ASC or DESC)
