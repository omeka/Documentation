--------------------------
Omeka_File_MimeType_Detect
--------------------------

.. php:class:: Omeka_File_MimeType_Detect

    Represents the detected MIME types of a file.

    .. php:attr:: _file
    


    .. php:attr:: _strategies
    


    .. php:attr:: _mimeType
    


    .. php:attr:: _mimeTypes
    


    .. php:attr:: _ambiguousMimeTypes
    


    .. php:method:: __construct(string|File $file, array $strategies = Array)
    
        Set the required properties for detecting the MIME types of a file.
        
        :param string|File $file: The full path to the file or a File record.
        :param array $strategies: An array of file detection strategies in priority order. If none are passed, a default list will be set. All strategies must implement Omeka_File_MimeType_Detect_StrategyInterface.

    .. php:method:: detect()
    
        Detect the MIME type of this file.
        
        :returns: string The definitive MIME type.

    .. php:method:: getMimeType()
    
        Get the definitive MIME type of this file.
        
        :returns: string

    .. php:method:: getMimeTypes()
    
        Get the MIME types of this file, one for each detection strategy.
        
        :returns: array