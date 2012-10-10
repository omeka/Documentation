-------------
Table_Element
-------------

.. php:class:: Table_Element

    .. php:method:: findByRecordType($recordTypeName)
    
        Find all the Element records that have a specific record type or the
        record type 'All', indicating that these elements would apply to any
        record type.
        
        :param unknown $recordTypeName: 
        :returns: array

    .. php:method:: getSelect()
    
        Overriding getSelect() to always return the type_name and type_regex
        for retrieved elements.
        
        :returns: Omeka_Db_Select

    .. php:method:: _getColumnPairs()
    
        Return the element's name and id for <select> tags on it.
        
        :returns: void

    .. php:method:: orderElements($select)
    
        :param unknown $select:

    .. php:method:: findBySet($elementSet)
    
        Retrieve all elements for a set.
        
        :param unknown $elementSet: 
        :returns: Element

    .. php:method:: findByItemType($itemTypeId)
    
        Retrieve a set of Element records that belong to a specific Item Type.
        
        :param unknown $itemTypeId: 
        :returns: array Set of element records.

    .. php:method:: findByElementSetNameAndElementName($elementSetName, $elementName)
    
        :param unknown $elementSetName: 
        :param unknown $elementName:

    .. php:method:: applySearchFilters(Omeka_Db_Select $select, array $params)
    
        Manipulate a Select object based on a set of criteria.
        
        :param Omeka_Db_Select $select: 
        :param array $params: Possible parameters include:         
        
            .. raw:: html
        
               <ul>
                      <li>record_types - array - Usually one or more of the following:
                 All, Item, File</li>
                      <li>sort - string - One of the following values: alpha</li>
                      <li>element_set_name - string - Name of the element set to which
                 results should belong.</li>
                 </ul>

    .. php:method:: findPairsForSelectForm(array $options = Array)
    
        Override parent class method to retrieve a multidimensional array of 
        elements, organized by element set, to be used in Zend's FormSelect view 
        helper.
        
        :param array $options: Set of parameters for searching/filtering results.
        :returns: array