-------------
Omeka_Storage
-------------

Package: :doc:`Storage </Reference/packages/Storage/index>`

.. php:class:: Omeka_Storage

    Top-level helper class for handling file storage.

    .. php:method:: __construct($options = null)

        Allows storage options to be set immediately at construction.

        :type $options: array
        :param $options: If set, this array will be passed to setOptions.

    .. php:method:: __call($name, $arguments)

        Delegates calls directly to Omeka_Storage to the currently-set
        storage adapter.

        All of the methods of the Adapter interface are accessible in this way, as
        well as any other methods declared by the adapter.

        :type $name: string
        :param $name: Method name.
        :type $arguments: string
        :param $arguments: Method arguments.
        :returns: mixed

    .. php:method:: setOptions($options)

        Set global options for the storage system, as well as any
        adapter-specific options.

        :type $options: array
        :param $options: Options to set. Valid options include: * 'adapter': (string) Name of the storage adapter to use. * 'adapterOptions': (array) Array of options to pass to the adapter; see the specific adapter classes for details. * 'temp_dir': (string) Local temporary directory where files stored before they are handled by the adapter.

    .. php:method:: setAdapter($adapter, $options = array())

        Set the storage adapter to be used, as well as options for that
        adapter.

        You can either pass an already-constructed adapter object to this method
        or use this method as a factory by passing the name of an adapter class
        and options to set on it.

        :type $adapter: Omeka_Storage_Adapter_AdapterInterface|string
        :param $adapter: Storage adapter to set. If an adapter object is passed, it is simply set as the current adapter. If a string is passed, an object of that class is created and set as the current adapter.
        :type $options: array|null
        :param $options: If a string is passed to $adapter, this array of options is passed to the class' constructor.

    .. php:method:: getAdapter()

        Get the current storage adapter.

        You generally need to use the adapter object returned by this method to
        perform any storage actions.

        :returns: Omeka_Storage_Adapter_AdapterInterface

    .. php:method:: setTempDir($dir)

        Set the temporary file storage directory path.

        :type $dir: string
        :param $dir: Local path to directory.

    .. php:method:: getTempDir()

        Get the temporary file storage directory path.

        If no directory has been explicitly selected, the system's temp directory
        is set as the temp dir and returned.

        :returns: string Local path to directory.

    .. php:method:: getPathByType($filename, $type = 'files')

        :param $filename:
        :param $type:
