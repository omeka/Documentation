---------------------------------------
Omeka_File_Derivative_StrategyInterface
---------------------------------------

.. php:class:: Omeka_File_Derivative_StrategyInterface

    Interface for pluggable file derivative creation strategies.

    .. php:method:: createImage(string $sourcePath, string $destPath, string $type, int $sizeConstraint, string $mimeType)
    
        Create an derivative of the given image.
        
        :param string $sourcePath: Local path to the source file.
        :param string $destPath: Local path to write the derivative to.
        :param string $type: The type of derivative being created.
        :param int $sizeConstraint: Size limitation on the derivative.
        :param string $mimeType: MIME type of the original file.
        :returns: bool

    .. php:method:: setOptions(array $options)
    
        Set options for the derivative strategy.
        
        :param array $options:

    .. php:method:: getOptions()
    
        Get the options for the strategy.
        
        :returns: array