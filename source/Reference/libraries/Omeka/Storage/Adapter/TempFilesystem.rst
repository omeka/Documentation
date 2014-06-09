------------------------------------
Omeka_Storage_Adapter_TempFilesystem
------------------------------------

.. php:class:: Omeka_Storage_Adapter_TempFilesystem

    Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

    Storage adapter that uses the system temp directory for its filesystem.
    
    After the adapter is no longer needed (__destruct()), all the files that were created during its lifetime are removed.
    
    Used primarily by the test framework.

    .. php:attr:: _localDir
    
        Local directory where files are stored.

    .. php:attr:: _subDirs
    


    .. php:attr:: _webDir
    
        Web-accesible path that corresponds to $_localDir.

    .. php:method:: canStore()
    
        No need to perform this check.

    .. php:method:: store(string $source, string $dest)
    
        Move a local file to "storage."
        
        :param string $source: Local filesystem path to file.
        :param string $dest: Destination path.

    .. php:method:: move(string $source, string $dest)
    
        Move a file between two "storage" locations.
        
        :param string $source: Original stored path.
        :param string $dest: Destination stored path.

    .. php:method:: getUri($path)
    
        :param unknown $path:

    .. php:method:: _mkdir($filepath)
    
        :param unknown $filepath:

    .. php:method:: __construct(array $options)
    
        Set options for the storage adapter.
        
        :param array $options:

    .. php:method:: setUp()

    .. php:method:: delete(string $path)
    
        Remove a "stored" file.
        
        :param string $path:

    .. php:method:: getOptions()
    
        Return the options set by the adapter.  Used primarily for testing.

    .. php:method:: setLocalDir($dir)
    
        Set the path of the local directory where files are stored.
        
        :param unknown $dir:

    .. php:method:: setWebDir($dir)
    
        Set the web URL that corresponds with the local dir.
        
        :param unknown $dir:

    .. php:method:: _getAbsPath(string $path)
    
        Convert a "storage" path to an absolute filesystem path.
        
        :param string $path: Storage path.
        :returns: string Absolute local filesystem path.

    .. php:method:: _rename($source, $dest)
    
        :param unknown $source: 
        :param unknown $dest: 
        :returns: boolean