----
File
----

.. php:class:: File

    Represents a file and its metadata.

    .. php:attr:: item_id
    


    .. php:attr:: order
    


    .. php:attr:: filename
    


    .. php:attr:: original_filename
    


    .. php:attr:: size
    


    .. php:attr:: authentication
    


    .. php:attr:: mime_browser
    


    .. php:attr:: mime_os
    


    .. php:attr:: type_os
    


    .. php:attr:: has_derivative_image
    


    .. php:attr:: added
    


    .. php:attr:: modified
    


    .. php:attr:: stored
    


    .. php:attr:: metadata
    


    .. php:attr:: _pathsByType
    


    .. php:method:: getProperty(string $property)
    
        Get a file's property for display.
        
        Available properties:
        - id
        - filename
        - original filename
        - size
        - mime type
        - date added
        - date modified
        - authentication
        - mime type os
        - file type os
        - uri
        - fullsize uri
        - thumbnail uri
        - square thumbnail uri
        - permalink
        
        :param string $property: 
        :returns: mixed

    .. php:method:: _initializeMixins()

    .. php:method:: filterPostData($post)
    
        :param unknown $post:

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: getItem()

    .. php:method:: getPath($type = original)
    
        Retrieve the path for the file
        
        :param unknown $type: 
        :returns: string

    .. php:method:: getWebPath($type = original)
    
        Retrieve the web path for the file
        
        :param unknown $type: 
        :returns: void

    .. php:method:: getDerivativeFilename()

    .. php:method:: hasThumbnail()

    .. php:method:: getExtension()

    .. php:method:: hasFullsize()

    .. php:method:: setDefaults($filepath, $options = Array)
    
        Set the default values that will be stored for this file in the 'files' table.
        
        These values include 'size', 'authentication', 'mime_browser', 'mime_os', 'type_os'
        and 'filename.
        
        :param unknown $filepath: 
        :param unknown $options: 
        :returns: void

    .. php:method:: getMimeType()
    
        Retrieve the definitive MIME type for this file.
        
        :returns: string

    .. php:method:: setMimeType($mimeType)
    
        :param unknown $mimeType: 
        :returns: void

    .. php:method:: _filterMimeType(string $mimeType)
    
        Filters the mime type.  In particular, it removes the charset information.
        
        :param string $mimeType: The raw mime type
        :returns: string Filtered mime type.

    .. php:method:: unlinkFile()

    .. php:method:: _delete()

    .. php:method:: createDerivatives()

    .. php:method:: extractMetadata()
    
        Extract ID3 metadata associated with the file.
        
        :returns: boolean

    .. php:method:: _setMimeTypeIfAmbiguous()
    
        Sets the MIME type for the file to the one detected by getID3, but only
        if the existing MIME type is 'ambiguous' and getID3 can detect a better
        one.

    .. php:method:: _getId3()
    
        Pull down the file's extra metadata via getID3 library.
        
        :returns: getID3

    .. php:method:: storeFiles()

    .. php:method:: getStoragePath($type = fullsize)
    
        :param unknown $type:

    .. php:method:: setStorage($storage)
    
        :param unknown $storage:

    .. php:method:: getStorage()

    .. php:method:: getResourceId()
    
        Get the ACL resource ID for the record.
        
        File records are 'Files' resources.
        
        :returns: string

    .. php:method:: isOwnedBy(User $user)
    
        Return whether this file is owned by the given user.
        
        Proxies to the Item's isOwnedBy.
        
        :param User $user: 
        :returns: boolean

    .. php:method:: afterSave($args)
    
        :param unknown $args:

