--------------------------------
Omeka_View_Helper_HasLoopRecords
--------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_HasLoopRecords

extends :php:class:`Zend_View_Helper_Abstract`

    .. php:method:: hasLoopRecords($recordsVar)

        Check if records have been set to the view for iteration.

        Note that this method will return false if the records variable is set but
        is an empty array, unlike
        Omeka_View_Helper_GetLoopRecords::getLoopRecords(),
        which will return the empty array.

        :type $recordsVar: string
        :param $recordsVar:
        :returns: bool
