--------------------------------
Omeka_View_Helper_HasLoopRecords
--------------------------------

.. php:class:: Omeka_View_Helper_HasLoopRecords

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    .. php:method:: hasLoopRecords(string $recordsVar)
    
        Check if records have been set to the view for iteration.
        
        Note that this method will return false if the records variable is setbut is an empty array, unlike Omeka_View_Helper_GetLoopRecords::getLoopRecords(),which will return the empty array.
        
        :param string $recordsVar: 
        :returns: bool