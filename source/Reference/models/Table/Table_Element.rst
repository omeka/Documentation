-------------
Table_Element
-------------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_Element

extends :php:class:`Omeka_Db_Table`

    .. php:method:: findByRecordType($recordTypeName)

        Find all the Element records that have a specific record type or the
        record type 'All', indicating that these elements would apply to any
        record type.

        :param $recordTypeName:
        :returns: array

    .. php:method:: getSelect()

        Overriding getSelect() to always return the type_name and type_regex
        for retrieved elements.

        :returns: Omeka_Db_Select

    .. php:method:: _getColumnPairs()

        Return the element's name and id for <select> tags on it.

        :returns: void

    .. php:method:: orderElements($select)

        :param $select:

    .. php:method:: findBySet($elementSet)

        Retrieve all elements for a set.

        :param $elementSet:
        :returns: Element

    .. php:method:: findByItemType($itemTypeId)

        Retrieve a set of Element records that belong to a specific Item Type.

        :param $itemTypeId:
        :returns: array Set of element records.

    .. php:method:: findByElementSetNameAndElementName($elementSetName, $elementName)

        :param $elementSetName:
        :param $elementName:

    .. php:method:: applySearchFilters($select, $params)

        Manipulate a Select object based on a set of criteria.

        :type $select: Omeka_Db_Select
        :param $select:
        :type $params: array
        :param $params: Possible parameters include: <ul> <li>record_types - array - Usually one or more of the following: All, Item, File</li> <li>sort - string - One of the following values: alpha</li> <li>element_set_name - string - Name of the element set to which results should belong.</li> </ul>

    .. php:method:: findPairsForSelectForm($options = array())

        Override parent class method to retrieve a multidimensional array of
        elements, organized by element set, to be used in Zend's FormSelect view
        helper.

        :type $options: array
        :param $options: Set of parameters for searching/filtering results.
        :returns: array
