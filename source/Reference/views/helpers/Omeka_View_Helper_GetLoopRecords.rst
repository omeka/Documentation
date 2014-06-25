--------------------------------
Omeka_View_Helper_GetLoopRecords
--------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_GetLoopRecords

extends :php:class:`Zend_View_Helper_Abstract`

    .. php:method:: getLoopRecords($recordsVar, $throwException = true)

        Get records from the view for iteration.

        Note that this method will return an empty array if it is set to the
        records variable. Use Omeka_View_Helper_HasLoopRecords::hasLoopRecords()
        to check if records exist.

        :type $recordsVar: string
        :param $recordsVar:
        :param $throwException:
        :returns: array|bool
