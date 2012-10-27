----
File
----

.. php:class:: File

    Package: :doc:`Record </Reference/packages/Record/index>`

    A file and its metadata.

    .. php:attr:: item_id
    


    .. php:attr:: order
    


    .. php:attr:: filename
    


    .. php:attr:: original_filename
    


    .. php:attr:: size
    


    .. php:attr:: authentication
    


    .. php:attr:: mime_type
    


    .. php:attr:: type_os
    


    .. php:attr:: has_derivative_image
    


    .. php:attr:: added
    


    .. php:attr:: modified
    


    .. php:attr:: stored
    


    .. php:attr:: metadata
    


    .. php:attr:: _pathsByType
    


    .. php:method:: getProperty(string $property)
    
        Get a property or special value of this record.
        
        :param string $property: 
        :returns: mixed

    .. php:method:: _initializeMixins()
    
        Initialize mixins.

    .. php:method:: filterPostData(array $post)
    
        Unset immutable properties from $_POST.
        
        :param array $post: 
        :returns: array

    .. php:method:: beforeSave(array $args)
    
        Do something before saving this record.
        
        :param array $args:

    .. php:method:: afterSave(array $args)
    
        Do something after saving this record.
        
        :param array $args:

    .. php:method:: getItem()
    
        Retrieve the parent item of this record.
        
        :returns: Item

    .. php:method:: getPath(string $type = original)
    
        Retrieve a system path for this file.
        
        :param string $type: 
        :returns: string

    .. php:method:: getWebPath(string $type = original)
    
        Retrieve a web path for this file.
        
        :param string $type: 
        :returns: string

    .. php:method:: getDerivativeFilename()
    
        Retrieve the derivative filename.
        
        :returns: string

    .. php:method:: hasThumbnail()
    
        Determine whether this record has a thumbnail image.
        
        :returns: bool

    .. php:method:: hasFullsize()
    
        Determine whether this record has a fullsize image.
        
        :returns: bool

    .. php:method:: getExtension()
    
        Get the original file's extension.
        
        :returns: string

    .. php:method:: setDefaults($filepath, $options = Array)
    
        Set the default values that will be stored for this record in the 'files' 
        table.
        
        :param unknown $filepath: 
        :param unknown $options: 
        :returns: void

    .. php:method:: unlinkFile()
    
        Unlink the file and file derivatives belonging to this record.

    .. php:method:: _delete()
    
        Perform any further deletion when deleting this record.

    .. php:method:: createDerivatives()
    
        Create derivatives of the original file.

    .. php:method:: extractMetadata()
    
        Extract ID3 metadata associated with the file.
        
        :returns: boolean

    .. php:method:: _getId3()
    
        Pull down the file's extra metadata via getID3 library.
        
        :returns: getID3

    .. php:method:: storeFiles()
    
        Store files belonging to this record.

    .. php:method:: getStoragePath(string $type = fullsize)
    
        Get the storage path.
        
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
        :returns: boolean