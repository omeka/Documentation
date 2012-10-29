----------------------------
Omeka_Validate_File_MimeType
----------------------------

.. php:class:: Omeka_Validate_File_MimeType

    Package: :doc:`Validate </Reference/packages/Validate/index>`

    Validates files against a MIME type whitelist.

    .. php:attr:: _messageTemplates
    


    .. php:attr:: _messageVariables
    


    .. php:attr:: _customWhitelist
    


    .. php:attr:: _file
    


    .. php:attr:: _mimeType
    


    .. php:method:: __construct()
    
        Construct the validator object.

    .. php:method:: isValid(string $file)
    
        Vaidate the file MIME type.
        
        :param string $file: 
        :returns: bool