------------------------
Omeka_File_Ingest_Upload
------------------------

.. php:class:: Omeka_File_Ingest_Upload

    This class creates a bridge between the ZF File Transfer HTTP adapter and
    Omeka's file ingest classes.

    .. php:attr:: _adapter
    


    .. php:attr:: _adapterOptions
    


    .. php:attr:: _item
    


    .. php:attr:: _options
    
        Set of arbitrary options to use when ingesting files.

    .. php:attr:: _validators
    
        Set of validators implementing Zend_Validate_Interface.

    .. php:attr:: mimeType
    
        The current validated file MIME type.

    .. php:method:: _buildAdapter()
    
        Create a ZF HTTP file transfer adapter.
        
        :returns: void

    .. php:method:: setOptions(array $options)
    
        In addition to the default options available for 
        Omeka_File_Ingest_AbstractIngest, this understands the following options:
        - 'ignoreNoFile' => boolean False by default.  Whether or not to ignore 
        - validation errors that occur when an uploaded file is missing.  This 
        - may occur when a file input is left empty on a form.
        
        This option can be overridden by the 'ignore_invalid_files' option.  For instance, if 'ignoreNoFile' is set to false
        but 'ignore_invalid_files' is set to true, any exceptions due to missing uploads will be suppressed and ignored.
        
        :param array $options: 
        :returns: void

    .. php:method:: _getOriginalFilename(array $fileInfo)
    
        The 'name' attribute of the $_FILES array will always contain the 
        original name of the file.
        
        :param array $fileInfo: 
        :returns: string

    .. php:method:: _transferFile(array $fileInfo, string $originalFilename)
    
        Use the Zend_File_Transfer adapter to upload the file.
        
        :param array $fileInfo: 
        :param string $originalFilename: 
        :returns: string Path to the file in Omeka.

    .. php:method:: _parseFileInfo(string|null $fileInfo)
    
        Use the adapter to extract the array of file information.
        
        :param string|null $fileInfo: The name of the form input to ingest.
        :returns: array

    .. php:method:: addValidator(Zend_Validate_Interface $validator)
    
        Use the Zend Framework adapter to handle validation instead of the 
        built-in _validateFile() method.
        
        :param Zend_Validate_Interface $validator: 
        :returns: void

    .. php:method:: setItem(Item $item)
    
        Set the item to use as a target when ingesting files.
        
        :param Item $item: 
        :returns: void

    .. php:method:: factory(string $adapterName, Item $item, array $options = Array)
    
        Factory to retrieve Omeka_File_Ingest_* instances.
        
        :param string $adapterName: Ingest adapter.
        :param Item $item: 
        :param array $options: 
        :returns: Omeka_File_Ingest_AbstractIngest

    .. php:method:: ingest(mixed $fileInfo)
    
        Ingest based on arbitrary file identifier info.
        
        If this is an array that has a 'metadata' key, that should be an array representing element text metadata to assign
        to the file.  See ActsAsElementText::addElementTextsByArray() for more details.
        
        :param mixed $fileInfo: An arbitrary input (array, string, object, etc.) that corresponds to one or more files to be ingested into Omeka.
        :returns: array Ingested file records.

    .. php:method:: _ignoreIngestErrors()
    
        Determine whether or not to ignore file ingest errors.  Based on 
        'ignore_invalid_files', which is false by default.
        
        :returns: boolean

    .. php:method:: _logException(Exception $e)
    
        Log any exceptions that are thrown as a result of attempting to ingest
        invalid files.
        
        These are logged as warnings because they are being ignored by the script,
        so they don't actually kill the file ingest process.
        
        :param Exception $e: 
        :returns: void

    .. php:method:: _createFile(string $newFilePath, string $oldFilename, array $elementMetadata = Array)
    
        Insert a File record corresponding to an ingested file and its metadata.
        
        :param string $newFilePath: Path to the file within Omeka.
        :param string $oldFilename: The original filename for the file.  This will usually be displayed to the end user.
        :param array $elementMetadata: See ActsAsElementText::addElementTextsByArray() for more information about the format of this array.
        :returns: File

    .. php:method:: _getDestination(string $fromFilename)
    
        Retrieve the destination path for the file to be transferred.
        
        This will generate an archival filename in order to prevent naming conflicts between ingested files.
        
        This should be used as necessary by Omeka_File_Ingest_AbstractIngest implementations in order to determine where to
        transfer any given file.
        
        :param string $fromFilename: The filename from which to derive the archival filename.
        :returns: string

    .. php:method:: _validateFile(string $filePath, array $fileInfo)
    
        Validate a file that has been transferred to Omeka.
        
        Implementations of Omeka_File_Ingest_AbstractIngest should use this to validate the uploaded file based on
        user-defined security criteria.
        
        Important: $fileInfo may need to contain the following keys in order to work with particular Zend_Validate_File_*
        validation classes:
        - 'name': string filename (for Zend_Validate_File_Extension) If ZF is unable to determine the file extension when
        validating, it will check the 'name' attribute instead.  Current use cases involve saving the file to a temporary
        location before transferring to Omeka. Most temporary files do not maintain the original file extension.
        - 'type': string MIME type (for Zend_Validate_File_MimeType) If ZF is unable to determine the mime type from the
        transferred file.  Unless the server running Omeka has a mime_magic file or has installed the FileInfo extension,
        this will be necessary.
        
        :param string $filePath: Absolute path to the file.  The file should be local and readable, which is required by most (if not all) of the Zend_Validate_File_* classes.
        :param array $fileInfo: Set of file info that describes a given file being ingested.
        :returns: boolean True if valid, otherwise throws an exception.