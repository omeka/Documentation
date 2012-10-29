--------------------------------------
Omeka_Storage_Adapter_AdapterInterface
--------------------------------------

.. php:class:: Omeka_Storage_Adapter_AdapterInterface

    Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

    Interface for file storage adapters.
    
    Classes that implement this interface handle the actual work ofstoring andretrieving files.

    .. php:method:: __construct(array $options)
    
        Set options for the storage adapter.
        
        :param array $options:

    .. php:method:: setUp()
    
        Follow any necessary steps to set up storage prior to use.
        
        E.g. for the filesystem adapter, this would include creating anydirectories that did not already exist.  For S3, it
        might involvecreating a new bucket if it did not exist.

    .. php:method:: canStore()
    
        Check whether the adapter is set up correctly to be able to store
        files.
        
        :returns: boolean

    .. php:method:: store(string $source, string $dest)
    
        Move a local file to "storage."
        
        :param string $source: Local filesystem path to file.
        :param string $dest: Destination path.

    .. php:method:: move(string $source, string $dest)
    
        Move a file between two storage locations.
        
        :param string $source: Original storage path.
        :param string $dest: Destination storage path.

    .. php:method:: delete(string $path)
    
        Remove a "stored" file.
        
        :param string $path:

    .. php:method:: getUri(string $path)
    
        Get a URI for a "stored" file.
        
        :param string $path: 
        :returns: string URI