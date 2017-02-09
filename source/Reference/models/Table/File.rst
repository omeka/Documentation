----------
Table_File
----------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_File

extends :php:class:`Omeka_Db_Table`

    .. php:attr:: _target

        protected

    .. php:method:: applySearchFilters($select, $params)

        :param $select:
        :param $params:

    .. php:method:: filterByHasDerivativeImage($select, $hasDerivative)

        :param $select:
        :param $hasDerivative:

    .. php:method:: getSelect()

        All files should only be retrieved if they join properly on the items
        table.

        :returns: Omeka_Db_Select

    .. php:method:: getRandomFileWithImage($itemId)

        Retrieve a random file with an image associated with an item.

        :type $itemId: integer
        :param $itemId:
        :returns: File

    .. php:method:: findByItem($itemId, $fileIds = array(), $sort = 'order')

        Retrieve files associated with an item.

        :type $itemId: integer
        :param $itemId:
        :type $fileIds: array
        :param $fileIds: Optional If given, this will only retrieve files with these specific IDs.
        :type $sort: string
        :param $sort: The manner by which to order the files. For example: 'id': file id, 'filename' = alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: array

    .. php:method:: findOneByItem($itemId, $index = 0, $sort = 'order')

        Get a single file associated with an item, by index.

        :type $itemId: integer
        :param $itemId:
        :type $index: integer
        :param $index:
        :type $sort: string
        :param $sort: The manner by which to order the files. For example: 'id': file id, 'filename' = alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: File|null

    .. php:method:: findWithImages($itemId, $index = null, $sort = 'order')

        Retrieve files for an item that has derivative images.

        :type $itemId: integer
        :param $itemId: The ID of the item to get images for.
        :type $index: integer|null
        :param $index: Optional If given, this specifies the file to retrieve for an item, based upon the ordering of its files.
        :type $sort: string
        :param $sort: The manner by which to order the files. For example: 'id': file id, 'filename': alphabetical by filename. The default is 'order', following the user's specified order.
        :returns: File|array

    .. php:method:: _orderFilesBy($select, $sort)

        Orders select results for files.

        :param $select:
        :type $sort: string
        :param $sort: The manner in which to order the files by. For example: 'id' = file id 'filename' = alphabetical by filename
        :returns: void
