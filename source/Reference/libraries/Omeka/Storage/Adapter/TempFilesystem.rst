------------------------------------
Omeka_Storage_Adapter_TempFilesystem
------------------------------------

Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

.. php:class:: Omeka_Storage_Adapter_TempFilesystem

extends :php:class:`Omeka_Storage_Adapter_Filesystem`

implements :php:interface:`Omeka_Storage_Adapter_AdapterInterface`

    Storage adapter that uses the system temp directory for its filesystem.

    After the adapter is no longer needed (__destruct()), all the files that were created during its lifetime are removed.

    Used primarily by the test framework.

    .. php:attr:: _localDir

        protected string

        Local directory where files are stored.

    .. php:attr:: _subDirs

        protected

    .. php:attr:: _webDir

        protected string

        Web-accesible path that corresponds to $_localDir.

    .. php:method:: canStore()

        No need to perform this check.

    .. php:method:: store($source, $dest)

        Move a local file to "storage."

        :type $source: string
        :param $source: Local filesystem path to file.
        :type $dest: string
        :param $dest: Destination path.

    .. php:method:: move($source, $dest)

        Move a file between two "storage" locations.

        :type $source: string
        :param $source: Original stored path.
        :type $dest: string
        :param $dest: Destination stored path.

    .. php:method:: getUri($path)

        :param $path:

    .. php:method:: _mkdir($filepath)

        :param $filepath:

    .. php:method:: __construct($options = array())

        Set options for the storage adapter.

        :type $options: array
        :param $options:

    .. php:method:: setUp()

    .. php:method:: delete($path)

        Remove a "stored" file.

        :type $path: string
        :param $path:

    .. php:method:: getOptions()

        Return the options set by the adapter.  Used primarily for testing.

    .. php:method:: setLocalDir($dir)

        Set the path of the local directory where files are stored.

        :param $dir:

    .. php:method:: setWebDir($dir)

        Set the web URL that corresponds with the local dir.

        :param $dir:

    .. php:method:: _getAbsPath($path)

        Convert a "storage" path to an absolute filesystem path.

        :type $path: string
        :param $path: Storage path.
        :returns: string Absolute local filesystem path.

    .. php:method:: _rename($source, $dest)

        :param $source:
        :param $dest:
        :returns: bool
