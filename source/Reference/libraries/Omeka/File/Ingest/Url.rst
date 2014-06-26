---------------------
Omeka_File_Ingest_Url
---------------------

Package: :doc:`File\\Ingest </Reference/packages/File/Ingest/index>`

.. php:class:: Omeka_File_Ingest_Url

extends :php:class:`Omeka_File_Ingest_AbstractSourceIngest`

    Ingest URLs into Omeka.

    .. php:attr:: _item

        protected Item

    .. php:attr:: _options

        protected array

        Set of arbitrary options to use when ingesting files.

    .. php:attr:: mimeType

        string

        The current validated file MIME type.

    .. php:method:: _getOriginalFilename($fileInfo)

        Return the original filename.

        :type $fileInfo: array
        :param $fileInfo:
        :returns: string

    .. php:method:: _getHttpClient($source)

        Get a HTTP client for retrieving the given file.

        :type $source: string
        :param $source: Source URI.
        :returns: Zend_Http_Client

    .. php:method:: _transfer($source, $destination, $fileInfo)

        Fetch a file from a URL.

        :type $source: string
        :param $source: Source URL.
        :type $destination: string
        :param $destination: Destination file path.
        :type $fileInfo: array
        :param $fileInfo:
        :returns: void

    .. php:method:: _validateSource($source, $info)

        Ensure the source URL exists and can be read from.

        :type $source: string
        :param $source: Source URL.
        :type $info: array
        :param $info: File info array (unused).
        :returns: void

    .. php:method:: _getFileSource($fileInfo)

        The 'source' key of the file info is parsed out by default.

        :param $fileInfo:
        :returns: string

    .. php:method:: _parseFileInfo($files)

        Normalize a file info array.

        Files can be represented as one of the following:
        - a string, representing the source identifier for a single file.
        - an array containing a 'source' key.
        - an array of strings.
        - an array of arrays that each contain a 'source' key.

        :type $files: string|array
        :param $files:
        :returns: array Formatted info array.

    .. php:method:: _addZendValidatorAttributes($fileInfo)

        Modify the set of info about each file to ensure that it is compatible
        with the Zend_Validate_File_* validators.

        :type $fileInfo: array
        :param $fileInfo:
        :returns: array

    .. php:method:: _transferFile($fileInfo, $originalFilename)

        Transfer the file to Omeka.

        :type $fileInfo: array
        :param $fileInfo:
        :type $originalFilename: string
        :param $originalFilename:
        :returns: string Path to file in Omeka.

    .. php:method:: setItem(Item $item)

        Set the item to use as a target when ingesting files.

        :type $item: Item
        :param $item:
        :returns: void

    .. php:method:: factory($adapterName, $item, $options = array())

        Factory to retrieve Omeka_File_Ingest_* instances.

        :type $adapterName: string
        :param $adapterName: Ingest adapter.
        :type $item: Item
        :param $item:
        :type $options: array
        :param $options:
        :returns: Omeka_File_Ingest_AbstractIngest

    .. php:method:: setOptions($options)

        Set options for ingesting files.

        :type $options: array
        :param $options: Available options include: - 'ignore_invalid_files': boolean false by default.  Determine whether or not to throw exceptions when a file is not valid.  This can be based on a number of factors:  whether or not the original identifier is valid (i.e. a valid URL), whether or not the file itself is valid (i.e. invalid file extension), or whether the basic algorithm for ingesting the file fails (i.e., files cannot be transferred because the files/ directory is not writeable). This option is primarily useful for skipping known invalid files when ingesting large data sets.
        :returns: void

    .. php:method:: ingest($fileInfo)

        Ingest based on arbitrary file identifier info.

        If this is an array that has a 'metadata' key, that should be an array
        representing element text metadata to assign to the file.  See
        ActsAsElementText::addElementTextsByArray() for more details.

        :type $fileInfo: mixed
        :param $fileInfo: An arbitrary input (array, string, object, etc.) that corresponds to one or more files to be ingested into Omeka.
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

        :type $e: Exception
        :param $e:
        :returns: void

    .. php:method:: _createFile($newFilePath, $oldFilename, $elementMetadata = array())

        Insert a File record corresponding to an ingested file and its metadata.

        :type $newFilePath: string
        :param $newFilePath: Path to the file within Omeka.
        :type $oldFilename: string
        :param $oldFilename: The original filename for the file.  This will usually be displayed to the end user.
        :type $elementMetadata: array
        :param $elementMetadata: See ActsAsElementText::addElementTextsByArray() for more information about the format of this array.
        :returns: File

    .. php:method:: _getDestination($fromFilename)

        Retrieve the destination path for the file to be transferred.

        This will generate an archival filename in order to prevent naming
        conflicts between ingested files.

        This should be used as necessary by Omeka_File_Ingest_AbstractIngest
        implementations in order to determine where to transfer any given file.

        :type $fromFilename: string
        :param $fromFilename: The filename from which to derive the archival filename.
        :returns: string

    .. php:method:: addValidator(Zend_Validate_Interface $validator)

        Add Zend Framework file validators.

        Emulates the way Zend Framework adds validators.

        :type $validator: Zend_Validate_Interface
        :param $validator:
        :returns: Omeka_File_Ingest_AbstractIngest

    .. php:method:: _validateFile($filePath, $fileInfo)

        Validate a file that has been transferred to Omeka.

        Implementations of Omeka_File_Ingest_AbstractIngest should use this to
        validate the uploaded file based on user-defined security criteria.

        Important: $fileInfo may need to contain the following keys in order to
        work with particular Zend_Validate_File_* validation classes:

        - 'name': string filename (for Zend_Validate_File_Extension) If ZF is
        unable to determine the file extension when validating, it will check the
        'name' attribute instead.  Current use cases involve saving the file to a
        temporary location before transferring to Omeka. Most temporary files do
        not maintain the original file extension.
        - 'type': string MIME type (for Zend_Validate_File_MimeType) If ZF is
        unable to determine the mime type from the transferred file.  Unless the
        server running Omeka has a mime_magic file or has installed the FileInfo
        extension, this will be necessary.

        :type $filePath: string
        :param $filePath: Absolute path to the file.  The file should be local and readable, which is required by most (if not all) of the Zend_Validate_File_* classes.
        :type $fileInfo: array
        :param $fileInfo: Set of file info that describes a given file being ingested.
        :returns: boolean True if valid, otherwise throws an exception.
