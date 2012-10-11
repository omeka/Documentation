-------------
Omeka_Storage
-------------

.. php:class:: Omeka_Storage

    Top-level helper class for handling file storage.

    .. php:attr:: _adapter
    


    .. php:attr:: _tempDir
    


    .. php:method:: __construct(array $options)
    
        Allows storage options to be set immediately at construction.
        
        :param array $options: If set, this array will be passed to setOptions.

    .. php:method:: __call(string $name, string $arguments)
    
        Delegates calls directly to Omeka_Storage to the currently-set
        storage adapter.
        
        All of the methods of the Adapter interface are accessible inthis way, as well as any other methods declared by the
        adapter.
        
        :param string $name: Method name.
        :param string $arguments: Method arguments.
        :returns: mixed

    .. php:method:: setOptions(array $options)
    
        Set global options for the storage system, as well as any
        adapter-specific options.
        
        :param array $options: Options to set. Valid options include: * 'adapter': (string) Name of the storage adapter to use. * 'adapterOptions': (array) Array of options to pass to the adapter; see the specific adapter classes for details. * 'temp_dir': (string) Local temporary directory where files stored before they are handled by the adapter.

    .. php:method:: setAdapter(Omeka_Storage_Adapter_AdapterInterface|string $adapter, array|null $options = Array)
    
        Set the storage adapter to be used, as well as options for that
        adapter.
        
        You can either pass an already-constructed adapter object to thismethod or use this method as a factory by passing
        the name of anadapter class and options to set on it.
        
        :param Omeka_Storage_Adapter_AdapterInterface|string $adapter: Storage adapter to set. If an adapter object is passed, it is simply set as the current adapter. If a string is passed, an object of that class is created and set as the current adapter.
        :param array|null $options: If a string is passed to $adapter, this array of options is passed to the class' constructor.

    .. php:method:: getAdapter()
    
        Get the current storage adapter.
        
        You generally need to use the adapter object returned by thismethod to perform any storage actions.
        
        :returns: Omeka_Storage_Adapter_AdapterInterface

    .. php:method:: setTempDir(string $dir)
    
        Set the temporary file storage directory path.
        
        :param string $dir: Local path to directory.

    .. php:method:: getTempDir()
    
        Get the temporary file storage directory path.
        
        If no directory has been explicitly selected, the system's tempdirectory is set as the temp dir and returned.
        
        :returns: string Local path to directory.

    .. php:method:: getPathByType($filename, $type = files)
    
        :param unknown $filename: 
        :param unknown $type: