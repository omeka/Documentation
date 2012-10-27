-----------------
Table_ElementText
-----------------

.. php:class:: Table_ElementText

    Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

    .. php:method:: getSelectForRecord($recordId, $recordType)
    
        :param unknown $recordId: 
        :param unknown $recordType: 
        :returns: Omeka_Db_Select

    .. php:method:: findByRecord(Omeka_Record_AbstractRecord $record)
    
        Find all ElementText records for a given database record (Item, File, etc).
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: array

    .. php:method:: findByElement($elementId)
    
        :param unknown $elementId: