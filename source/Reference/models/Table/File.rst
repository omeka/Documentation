----------
Table_File
----------

.. php:class:: Table_File

    Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

    .. php:attr:: _target
    


    .. php:method:: applySearchFilters($select, $params)
    
        :param unknown $select: 
        :param unknown $params:

    .. php:method:: filterBySince(Zend_Db_Select $select, string $dateSince, string $dateField)
    
        Filter select object by date since.
        
        :param Zend_Db_Select $select: 
        :param string $dateSince: ISO 8601 formatted date
        :param string $dateField: "added" or "modified"

    .. php:method:: filterByHasDerivativeImage($select, $hasDerivative)
    
        :param unknown $select: 
        :param unknown $hasDerivative:

    .. php:method:: getSelect()
    
        All files should only be retrieved if they join properly on the items
        table.
        
        :returns: Omeka_Db_Select

    .. php:method:: getRandomFileWithImage(integer $itemId)
    
        Retrieve a random file with an image associated with an item.
        
        :param integer $itemId: 
        :returns: File

    .. php:method:: findByItem(integer $itemId, array $fileIds, string $sort = order)
    
        Retrieve files associated with an item.
        
        :param integer $itemId: 
        :param array $fileIds: Optional If given, this will only retrieve files with these specific IDs.
        :param string $sort: The manner by which to order the files. For example: 'id': file id, 'filename' = alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: array

    .. php:method:: findOneByItem(integer $itemId, integer $index = 0, string $sort = order)
    
        Get a single file associated with an item, by index.
        
        :param integer $itemId: 
        :param integer $index: 
        :param string $sort: The manner by which to order the files. For example: 'id': file id, 'filename' = alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: File|null

    .. php:method:: findWithImages(integer $itemId, integer|null $index, string $sort = order)
    
        Retrieve files for an item that has derivative images.
        
        :param integer $itemId: The ID of the item to get images for.
        :param integer|null $index: Optional If given, this specifies the file to retrieve for an item, based upon the ordering of its files.
        :param string $sort: The manner by which to order the files. For example: 'id': file id, 'filename': alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: File|array

    .. php:method:: _orderFilesBy($select, string $sort)
    
        Orders select results for files.
        
        :param unknown $select: 
        :param string $sort: The manner in which to order the files by. For example: 'id' = file id 'filename' = alphabetical by filename
        :returns: void