--------------------------------
Omeka_File_Ingest_AbstractIngest
--------------------------------

.. php:class:: Omeka_File_Ingest_AbstractIngest

    An abstract class that handles ingesting files into Omeka and database.
    
    Specific responsibilities handled by this class:
    - Parsing/validating arbitrary inputs that somehow identify the files to be ingested.
    - Iterating through the parsed file information, validating, and transferring each file to Omeka.
    - Inserting a new record into the files table that corresponds to the transferred file's metadata.
    - Returning a collection of the records associated with the ingested files.
    
    Typical usage is via the factory() method:
    
        .. code-block:: php 
    
         $ingest = Omeka_File_Ingest_AbstractIngest::factory('Url', $item);
         $fileRecords = $ingest->ingest('http://www.example.com');

    .. php:attr:: _item
    


    .. php:attr:: _options
    
        Set of arbitrary options to use when ingesting files.

    .. php:attr:: _validators
    
        Set of validators implementing Zend_Validate_Interface.

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

    .. php:method:: _getOriginalFilename(array $fileInfo)
    
        Retrieve the original filename of the file.
        
        :param array $fileInfo: 
        :returns: string

    .. php:method:: _transferFile(array $fileInfo, string $originalFilename)
    
        Transfer the file to Omeka.
        
        To indicate validation errors, Omeka_File_Ingest_InvalidException can be thrown at any time.  To indicate other
        types of non-recoverable errors related to file ingest, throw Omeka_File_Ingest_Exception.
        
        :param array $fileInfo: 
        :param string $originalFilename: 
        :returns: string Real path to the transferred file.

    .. php:method:: _parseFileInfo(mixed $files)
    
        Ingest classes receive arbitrary information.  This method needs to
        parse that information into an iterable array so that multiple files
        can be ingested from a single identifier.
        
        Example use case is Omeka_File_Ingest_Upload.
        
        :param mixed $files: 
        :returns: array

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

