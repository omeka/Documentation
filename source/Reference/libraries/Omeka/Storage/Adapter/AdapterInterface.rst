--------------------------------------
Omeka_Storage_Adapter_AdapterInterface
--------------------------------------

Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

.. php:interface:: Omeka_Storage_Adapter_AdapterInterface

    Interface for file storage adapters.

    Classes that implement this interface handle the actual work ofstoring and retrieving files.

    .. php:method:: __construct($options = null)

        Set options for the storage adapter.

        :type $options: array
        :param $options:

    .. php:method:: setUp()

        Follow any necessary steps to set up storage prior to use.

        E.g. for the filesystem adapter, this would include creating any
        directories that did not already exist.  For S3, it might involve creating
        a new bucket if it did not exist.

    .. php:method:: canStore()

        Check whether the adapter is set up correctly to be able to store
        files.

        :returns: boolean

    .. php:method:: store($source, $dest)

        Move a local file to "storage."

        :type $source: string
        :param $source: Local filesystem path to file.
        :type $dest: string
        :param $dest: Destination path.

    .. php:method:: move($source, $dest)

        Move a file between two storage locations.

        :type $source: string
        :param $source: Original storage path.
        :type $dest: string
        :param $dest: Destination storage path.

    .. php:method:: delete($path)

        Remove a "stored" file.

        :type $path: string
        :param $path:

    .. php:method:: getUri($path)

        Get a URI for a "stored" file.

        :type $path: string
        :param $path:
        :returns: string URI
