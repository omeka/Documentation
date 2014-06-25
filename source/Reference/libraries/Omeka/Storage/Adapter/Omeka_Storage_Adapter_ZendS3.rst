----------------------------
Omeka_Storage_Adapter_ZendS3
----------------------------

Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

.. php:class:: Omeka_Storage_Adapter_ZendS3

implements :php:interface:`Omeka_Storage_Adapter_AdapterInterface`

    Cloud storage adapter for Amazon S3, using Zend's built-in service.

    Caveat: Zend's storage adapter currently does not function correctly with buckets that are validly-named, but use characters that cannot appear in domain names.

    .. php:method:: __construct($options = array())

        Set options for the storage adapter.

        :type $options: array
        :param $options:

    .. php:method:: setUp()

    .. php:method:: canStore()

    .. php:method:: store($source, $dest)

        Move a local file to S3 storage.

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

    .. php:method:: delete($path)

        Remove a "stored" file.

        :type $path: string
        :param $path:

    .. php:method:: getUri($path)

        Get a URI for a "stored" file.

        :type $path: string
        :param $path:
        :returns: string URI

    .. php:method:: getS3Service()

        Return the service object being used for S3 requests.

        :returns: Zend_Service_Amazon_S3

    .. php:method:: _getBucketName()

        Get the name of the bucket files should be stored in.

        :returns: string Bucket name

    .. php:method:: _getObjectName($path)

        Get the object name.  Zend's S3 service requires you to build the
        object name by prepending the name of the target bucket.

        :type $path: string
        :param $path:
        :returns: string Object name.

    .. php:method:: _getExpiration()

        Normalizes and returns the expiration time.

        Converts to integer and returns zero for all non-positive numbers.

        :returns: int
