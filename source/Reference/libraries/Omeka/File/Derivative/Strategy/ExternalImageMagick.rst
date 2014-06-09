--------------------------------------------------
Omeka_File_Derivative_Strategy_ExternalImageMagick
--------------------------------------------------

.. php:class:: Omeka_File_Derivative_Strategy_ExternalImageMagick

    Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

    Strategy for making derivatives with ImageMagick on the command line.

    .. php:attr:: _convertPath
    


    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)
    
        Generate a derivative image from an existing file stored in Omeka.
        
        This image will be generated based on a constraint given in pixels.  Forexample, if the constraint is 500, the resulting image file will be scaledso that the largest side is 500px. If the image is less than 500px on bothsides, the image will not be resized.
        
        Derivative images will only be generated for files with mime typesthat pass any configured blacklist and/or whitelist and can be processedby the convert binary.
        
        :param unknown $sourcePath: 
        :param unknown $destPath: 
        :param unknown $type: 
        :param unknown $sizeConstraint: 
        :param unknown $mimeType:

    .. php:method:: _getConvertPath()
    
        Get the full path to the ImageMagick 'convert' command.
        
        :returns: string

    .. php:method:: _getConvertArgs(string $type, int $constraint)
    
        Get the ImageMagick command line for resizing to the given constraints.
        
        :param string $type: Type of derivative being made.
        :param int $constraint: Maximum side length in pixels.
        :returns: string

    .. php:method:: isValidImageMagickPath($dirToIm)
    
        Determine whether or not the path given to ImageMagick is valid.
        The convert binary must be within the directory and executable.
        
        :param unknown $dirToIm: 
        :returns: boolean

    .. php:method:: getDefaultImageMagickDir()
    
        Retrieve the path to the directory containing ImageMagick's convert utility.
        
        Uses the 'which' command-line utility to detect the path to 'convert'.Note that this will only work if the convert utility is in PHP's PATH andthus can be located by 'which'.
        
        :returns: string The path to the directory if it can be found.  Otherwise returns an empty string.

    .. php:method:: executeCommand($cmd, $status, $output, $errors)
    
        :param unknown $cmd: 
        :param unknown $status: 
        :param unknown $output: 
        :param unknown $errors: