--------------------------------
Omeka_View_Helper_GetLoopRecords
--------------------------------

.. php:class:: Omeka_View_Helper_GetLoopRecords

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    .. php:method:: getLoopRecords(string $recordsVar, $throwException = 1)
    
        Get records from the view for iteration.
        
        Note that this method will return an empty array if it is set to therecords variable. Use Omeka_View_Helper_HasLoopRecords::hasLoopRecords()to check if records exist.
        
        :param string $recordsVar: 
        :param unknown $throwException: 
        :returns: array|bool