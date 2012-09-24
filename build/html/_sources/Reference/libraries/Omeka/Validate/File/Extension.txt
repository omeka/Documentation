-----------------------------
Omeka_Validate_File_Extension
-----------------------------

.. php:class:: Omeka_Validate_File_Extension

    Define custom behavior for the default whitelist file extension validator.
    
    Baseline behavior of this class is to tweak the default error messages.  
    Messages are intentionally as detailed as possible.  Note that it is the responsibility of plugin writers to suppress or replace these messages if necessary for security reasons, e.g. if displaying it to the end user might expose the site to vulnerability probes.

    .. php:attr:: _messageTemplates
    
        Overrides default error message templates.

    .. php:attr:: _targetExtension
    
        The extension of the file being validated

    .. php:method:: __construct(mixed $options)
    
        Constructor retrieves the whitelist from the database if no arguments are
        given.
        
        :param mixed $options: 
        :returns: void

    .. php:method:: isValid(string $value, array $file)
    
        Returns true if and only if the fileextension of $value is included in 
        the set extension list.
        
        :param string $value: Real file to check for extension.
        :param array $file: File data from Zend_File_Transfer.
        :returns: boolean

