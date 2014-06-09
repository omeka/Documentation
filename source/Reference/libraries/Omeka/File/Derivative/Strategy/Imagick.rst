--------------------------------------
Omeka_File_Derivative_Strategy_Imagick
--------------------------------------

.. php:class:: Omeka_File_Derivative_Strategy_Imagick

    Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

    Strategy for making derivatives with the Imagick PHP extension.
    
    The strategy requires ext/imagick.

    .. php:method:: __construct()
    
        Check for the imagick extension at creation.

    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)
    
        Generate a derivative image with Imagick.
        
        :param unknown $sourcePath: 
        :param unknown $destPath: 
        :param unknown $type: 
        :param unknown $sizeConstraint: 
        :param unknown $mimeType:

    .. php:method:: _getCropOffsetX(int $resizedX, int $sizeConstraint)
    
        Get the required crop offset on the X axis.
        
        This respects the 'gravity' setting.
        
        :param int $resizedX: Pre-crop image width
        :param int $sizeConstraint: 
        :returns: int

    .. php:method:: _getCropOffsetY(int $resizedY, int $sizeConstraint)
    
        Get the required crop offset on the Y axis.
        
        This respects the 'gravity' setting.
        
        :param int $resizedY: Pre-crop image height
        :param int $sizeConstraint: 
        :returns: int