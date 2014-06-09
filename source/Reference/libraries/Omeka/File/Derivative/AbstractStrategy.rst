--------------------------------------
Omeka_File_Derivative_AbstractStrategy
--------------------------------------

.. php:class:: Omeka_File_Derivative_AbstractStrategy

    Abstract class for pluggable file derivative creation strategies.

    .. php:attr:: _options
    


    .. php:method:: setOptions(array $options)
    
        Set options for the derivative strategy.
        
        :param array $options:

    .. php:method:: getOptions()
    
        Get the options for the strategy.
        
        :returns: array

    .. php:method:: getOption(string $name, mixed $default)
    
        Get the value for the specified option.
        
        :param string $name: Name of the option to get
        :param mixed $default: Default value to return if the option is missing. Defaults to null.
        :returns: mixed

    .. php:method:: createImage(string $sourcePath, string $destPath, string $type, int $sizeConstraint, string $mimeType)
    
        Create an derivative of the given image.
        
        :param string $sourcePath: Local path to the source file.
        :param string $destPath: Local path to write the derivative to.
        :param string $type: The type of derivative being created.
        :param int $sizeConstraint: Size limitation on the derivative.
        :param string $mimeType: MIME type of the original file.
        :returns: bool