----------------
Table_ElementSet
----------------

Package: :doc:`Db\\Table </Reference/packages/Db/Table/index>`

.. php:class:: Table_ElementSet

extends :php:class:`Omeka_Db_Table`

    .. php:method:: getSelect()

    .. php:method:: findByRecordType($recordTypeName, $includeAll = true)

        Find all the element sets that correspond to a particular record type.
        If the second param is set, this will include all element sets that belong

        to the 'All' record type.

        :param $recordTypeName:
        :param $includeAll:
        :returns: array

    .. php:method:: findByName($name)

        :param $name:
