----------------------------
Omeka_Validate_File_MimeType
----------------------------

.. php:class:: Omeka_Validate_File_MimeType

    Validates files against a MIME type whitelist.

    .. php:attr:: _messageTemplates
    
        Omeka-specific error messages for validating MIME types.
        Also fixes some grammatical errors in the original validator error 
        messages.

    .. php:method:: __construct(mixed $options)
    
        Constructor.
        
        Use the 'file_mime_type_whitelist' option if nothing is passed in as the default.
        
        :param mixed $options: 
        :returns: void