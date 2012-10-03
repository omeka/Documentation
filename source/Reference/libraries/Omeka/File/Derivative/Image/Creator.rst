-----------------------------------
Omeka_File_Derivative_Image_Creator
-----------------------------------

.. php:class:: Omeka_File_Derivative_Image_Creator

    Create derivative images for a file in Omeka.

    .. php:attr:: _convertPath
    


    .. php:attr:: _identifyPath
    


    .. php:attr:: _derivatives
    


    .. php:method:: __construct($imDirPath)
    
        :param unknown $imDirPath:

    .. php:method:: setImageMagickDirPath(string $imDirPath)
    
        Set the path to the ImageMagick executable.
        
        :param string $imDirPath: Path to the directory containing the ImageMagick binaries.

    .. php:method:: getConvertPath()
    
        Get the full path to the ImageMagick 'convert' command.
        
        :returns: string

    .. php:method:: getIdentifyPath()
    
        Get the full path to the ImageMagick 'identify' command.
        
        :returns: string

    .. php:method:: create(string $fromFilePath, string $derivFilename, string $mimeType)
    
        Create all the derivatives requested with addDerivative().
        
        :param string $fromFilePath: 
        :param string $derivFilename: 
        :param string $mimeType: 
        :returns: boolean

    .. php:method:: addDerivative(string $storageType, integer|string $size, boolean $square = )
    
        Add a derivative image to be created.
        
        :param string $storageType: 
        :param integer|string $size: If an integer, it is the size constraint for the image, meaning it will have that maximum width or height, depending on whether the image is landscape or portrait.  Otherwise, it is a string of arguments to be passed to the ImageMagick convert utility.  MUST BE PROPERLY ESCAPED AS SHELL ARGUMENTS.
        :param boolean $square: Whether the derivative to add should be made square.

    .. php:method:: _createImage($origPath, $newPath, $convertArgs)
    
        Generate a derivative image from an existing file stored in Omeka.
        
        This image will be generated based on a constraint given in pixels.  For example, if the constraint is 500, the
        resulting image file will be scaled so that the largest side is 500px. If the image is less than 500px on both
        sides, the image will not be resized.
        
        Derivative images will only be generated for files with mime types that can be identified with ImageMagick's
        'identify' command
        
        :param unknown $origPath: 
        :param unknown $newPath: 
        :param unknown $convertArgs:

    .. php:method:: _getResizeCmdArgs(integer $constraint, boolean $square)
    
        Get the ImageMagick command line for resizing to the given constraints.
        
        :param integer $constraint: Maximum side length in pixels.
        :param boolean $square: Whether the derivative should be squared off.
        :returns: string

    .. php:method:: _isDerivable(string $filePath)
    
        Returns true only if ImageMagick is able to make derivative images of that file based
        upon whether or not it can be identified by ImageMagick's 'identify' binary. Otherwise returns false.
        
        :param string $filePath: 
        :returns: boolean

    .. php:method:: _isIdentifiable(string $filePath)
    
        Returns true only if the file can be identified by ImageMagick's 'identify' binary
        
        :param string $filePath: 
        :returns: boolean

    .. php:method:: isValidImageMagickPath($dirToIm)
    
        Determine whether or not the path given to ImageMagick is valid.
        Both the convert and identify binaries must be within the directory and executable.
        
        :param unknown $dirToIm: 
        :returns: boolean

    .. php:method:: getDefaultImageMagickDir()
    
        Retrieve the path to the directory containing ImageMagick's convert utility.
        Th
        
        Uses the 'which' command-line utility to detect the path to 'convert'. 
        Note that this will only work if the convert utility is in PHP's PATH and thus can be located by 'which'.
        
        :returns: string The path to the directory if it can be found.  Otherwise returns an empty string.

    .. php:method:: executeCommand($cmd, $status, $output, $errors)
    
        :param unknown $cmd: 
        :param unknown $status: 
        :param unknown $output: 
        :param unknown $errors:

