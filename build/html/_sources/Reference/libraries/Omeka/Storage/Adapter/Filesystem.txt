--------------------------------
Omeka_Storage_Adapter_Filesystem
--------------------------------

.. php:class:: Omeka_Storage_Adapter_Filesystem

    Package: :doc:`/Reference/packages/Storage\Adapter/index`

    Standard local filesystem storage adapter.
    
    The default adapter; this stores files in the Omeka files directory bydefault, but can be set to point to a different path.

    .. php:attr:: _localDir
    
        Local directory where files are stored.

    .. php:attr:: _subDirs
    


    .. php:attr:: _webDir
    
        Web-accesible path that corresponds to $_localDir.

    .. php:method:: __construct(array $options = Array)
    
        Set options for the storage adapter.
        
        :param array $options:

    .. php:method:: setUp()

    .. php:method:: canStore()
    
        Check whether the adapter is set up correctly to be able to store
        files.
        
        Specifically, this checks to see if the local storage directoryis writable.
        
        :returns: boolean

    .. php:method:: store(string $source, string $dest)
    
        Move a local file to "storage."
        
        :param string $source: Local filesystem path to file.
        :param string $dest: Destination path.

    .. php:method:: move(string $source, string $dest)
    
        Move a file between two "storage" locations.
        
        :param string $source: Original stored path.
        :param string $dest: Destination stored path.

    .. php:method:: delete(string $path)
    
        Remove a "stored" file.
        
        :param string $path:

    .. php:method:: getUri(string $path)
    
        Get a URI for a "stored" file.
        
        :param string $path: 
        :returns: string URI

    .. php:method:: getOptions()
    
        Return the options set by the adapter.  Used primarily for testing.

    .. php:method:: setLocalDir($dir)
    
        :param unknown $dir:

    .. php:method:: _getAbsPath(string $path)
    
        Convert a "storage" path to an absolute filesystem path.
        
        :param string $path: Storage path.
        :returns: string Absolute local filesystem path.

    .. php:method:: _rename($source, $dest)
    
        :param unknown $source: 
        :param unknown $dest: 
        :returns: boolean