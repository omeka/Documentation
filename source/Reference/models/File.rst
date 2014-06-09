----
File
----

.. php:class:: File

    Package: :doc:`Record </Reference/packages/Record/index>`

    A file and its metadata.

    .. php:const:: DISABLE_DEFAULT_VALIDATION_OPTION
    
    
    
        Option name for whether the file validation is disabled.

    .. php:const:: DERIVATIVE_EXT
    
    
    
        File extension for all image derivatives.

    .. php:attr:: item_id
    
        ID of the Item this File belongs to.

    .. php:attr:: order
    
        Relative order of this File within the parent Item.

    .. php:attr:: filename
    
        Current filename, as stored.

    .. php:attr:: original_filename
    
        Original filename, as uploaded.

    .. php:attr:: size
    
        Size of the file, in bytes.

    .. php:attr:: authentication
    
        MD5 hash of the file.

    .. php:attr:: mime_type
    
        MIME type of the file.

    .. php:attr:: type_os
    
        Longer description of the file's type.

    .. php:attr:: has_derivative_image
    
        Whether the file has derivative images.

    .. php:attr:: added
    
        Date the file was added.

    .. php:attr:: modified
    
        Date the file was last modified.

    .. php:attr:: stored
    
        Whether the file has been moved to storage.

    .. php:attr:: metadata
    
        Embedded metadata from the file.

    .. php:attr:: _pathsByType
    
        Folder paths for each type of files/derivatives.

    .. php:method:: getProperty(string $property)
    
        Get a property or special value of this record.
        
        :param string $property: 
        :returns: mixed

    .. php:method:: _initializeMixins()
    
        Initialize the mixins.

    .. php:method:: filterPostData(array $post)
    
        Unset immutable properties from $_POST.
        
        :param array $post: 
        :returns: array

    .. php:method:: beforeSave(array $args)
    
        Before-save hook.
        
        :param array $args:

    .. php:method:: afterSave(array $args)
    
        After-save hook.
        
        :param array $args:

    .. php:method:: getItem()
    
        Get the Item this file belongs to.
        
        :returns: Item

    .. php:method:: getPath(string $type = original)
    
        Get a system path for this file.
        
        Local paths are only available before the file is stored.
        
        :param string $type: 
        :returns: string

    .. php:method:: getWebPath(string $type = original)
    
        Get a web path for this file.
        
        :param string $type: 
        :returns: string

    .. php:method:: getDerivativeFilename()
    
        Get the filename for this file's derivative images.
        
        :returns: string

    .. php:method:: hasThumbnail()
    
        Determine whether this file has a thumbnail image.
        
        :returns: bool

    .. php:method:: hasFullsize()
    
        Determine whether this record has a fullsize image.
        
        This is an alias for hasThumbnail().
        
        :returns: bool

    .. php:method:: getExtension()
    
        Get the original file's extension.
        
        :returns: string

    .. php:method:: setDefaults($filepath, $options)
    
        Set the default values that will be stored for this record in the 'files' 
        table.
        
        :param unknown $filepath: 
        :param unknown $options:

    .. php:method:: unlinkFile()
    
        Unlink the file and file derivatives belonging to this record.

    .. php:method:: _delete()
    
        Perform any further deletion when deleting this record.

    .. php:method:: createDerivatives()
    
        Create derivatives of the original file.

    .. php:method:: extractMetadata()
    
        Extract ID3 metadata associated with the file.
        
        :returns: bool Whether getID3 was able to read the file.

    .. php:method:: _getId3()
    
        Read the file's embedded metadata with the getID3 library.
        
        :returns: getID3|bool Returns getID3 object, or false if there was an exception.

    .. php:method:: storeFiles()
    
        Store the files belonging to this record.

    .. php:method:: getStoragePath(string $type = fullsize)
    
        Get a storage path for the file.
        
        :param string $type: 
        :returns: string

    .. php:method:: setStorage(Omeka_Storage $storage)
    
        Set the storage object.
        
        :param Omeka_Storage $storage:

    .. php:method:: getStorage()
    
        Get the storage object.
        
        :returns: Omeka_Storage

    .. php:method:: getResourceId()
    
        Get the ACL resource ID for the record.
        
        File records are 'Files' resources.
        
        :returns: string

    .. php:method:: isOwnedBy(User $user)
    
        Return whether this file is owned by the given user.
        
        Proxies to the Item's isOwnedBy.
        
        :param User $user: 
        :returns: bool

    .. php:method:: getFile()
    
        Return the representative File for the record (this File itself).
        
        :returns: File