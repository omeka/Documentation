-----------------------------
Omeka_View_Helper_MaxFileSize
-----------------------------

.. php:class:: Omeka_View_Helper_MaxFileSize

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    .. php:attr:: _maxFileSize
    


    .. php:method:: __construct()
    
        Set the maximum file size.
        
        The maximum file size is the least of the configurations that affect maximum file size.

    .. php:method:: maxFileSize()
    
        Return the maximum file size.
        
        :returns: Zend_Measure_Binary

    .. php:method:: _getSizeMeasure(string|int $size)
    
        Get the binary measurements for file size.
        
        :param string|int $size: 
        :returns: Zend_Measure_Binary