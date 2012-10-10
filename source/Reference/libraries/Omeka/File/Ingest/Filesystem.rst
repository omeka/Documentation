----------------------------
Omeka_File_Ingest_Filesystem
----------------------------

.. php:class:: Omeka_File_Ingest_Filesystem

    Implements ingesting files from the local filesystem.

    .. php:attr:: _item
    


    .. php:attr:: _options
    
        Set of arbitrary options to use when ingesting files.

    .. php:attr:: _validators
    
        Set of validators implementing Zend_Validate_Interface.

    .. php:attr:: mimeType
    
        The current validated file MIME type.

    .. php:method:: _getOriginalFilename(array $info)
    
        Retrieve the original filename of the file to be transferred.
        
        Check for the 'name' attribute first, otherwise extract the basename() 
        from the given file path.
        
        :param array $info: File info array.
        :returns: string

    .. php:method:: _transfer(string $source, string $destination, array $info)
    
        Transfer a file.
        
        :param string $source: Source path.
        :param string $destination: Destination path.
        :param array $info: File info array.  If 'rename' is specified as true, move the file instead of copying.
        :returns: void

    .. php:method:: _validateSource(string $source, array $info)
    
        Validate file transfer.
        
        :param string $source: Source path.
        :param array $info: File info array.

    .. php:method:: _getFileSource($fileInfo)
    
        The 'source' key of the file info is parsed out by default.
        
        :param unknown $fileInfo: 
        :returns: string

    .. php:method:: _parseFileInfo(string|array $files)
    
        Normalize a file info array.
        
        Files can be represented as one of the following: 
        - a string, representing the source identifier for a single file. 
        - an array containing a 'source' key.
        - an array of strings.
        - an array of arrays that each contain a 'source' key.
        
        :param string|array $files: 
        :returns: array Formatted info array.

    .. php:method:: _addZendValidatorAttributes(array $fileInfo)
    
        Modify the set of info about each file to ensure that it is compatible
        with the Zend_Validate_File_* validators.
        
        :param array $fileInfo: 
        :returns: array

    .. php:method:: _transferFile(array $fileInfo, string $originalFilename)
    
        Transfer the file to Omeka.
        
        :param array $fileInfo: 
        :param string $originalFilename: 
        :returns: string Path to file in Omeka.

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

    .. php:method:: setOptions(array $options)
    
        Set options for ingesting files.
        
        :param array $options: Available options include: - 'ignore_invalid_files': boolean false by default.  Determine whether or not to throw exceptions when a file is not valid.  This can be based on a number of factors:  whether or not the original identifier is valid (i.e. a valid URL), whether or not the file itself is valid (i.e. invalid file extension), or whether the basic algorithm for ingesting the file fails (i.e., files cannot be transferred because the files/ directory is not writeable). This option is primarily useful for skipping known invalid files when ingesting large data sets.
        :returns: void

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

    .. php:method:: addValidator(Zend_Validate_Interface $validator)
    
        Add Zend Framework file validators.
        
        Emulates the way Zend Framework adds validators.
        
        :param Zend_Validate_Interface $validator: 
        :returns: Omeka_File_Ingest_AbstractIngest

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