----------------------------
Omeka_Storage_Adapter_ZendS3
----------------------------

.. php:class:: Omeka_Storage_Adapter_ZendS3

    Package: :doc:`Storage\\Adapter </Reference/packages/Storage/Adapter/index>`

    Cloud storage adapter for Amazon S3, using Zend's built-in service.
    
    Caveat: Zend's storage adapter currently does not function correctlywith buckets that are validly-named, but use characters that cannotappear in domain names.

    .. php:attr:: _s3
    


    .. php:attr:: _options
    


    .. php:method:: __construct(array $options)
    
        Set options for the storage adapter.
        
        :param array $options:

    .. php:method:: setUp()

    .. php:method:: canStore()

    .. php:method:: store(string $source, string $dest)
    
        Move a local file to S3 storage.
        
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

    .. php:method:: getS3Service()
    
        Return the service object being used for S3 requests.
        
        :returns: Zend_Service_Amazon_S3

    .. php:method:: _getBucketName()
    
        Get the name of the bucket files should be stored in.
        
        :returns: string Bucket name

    .. php:method:: _getObjectName(string $path)
    
        Get the object name.  Zend's S3 service requires you to build the
        object name by prepending the name of the target bucket.
        
        :param string $path: 
        :returns: string Object name.

    .. php:method:: _getExpiration()
    
        Normalizes and returns the expiration time.
        
        Converts to integer and returns zero for all non-positive numbers.
        
        :returns: int