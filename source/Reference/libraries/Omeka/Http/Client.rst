-----------------
Omeka_Http_Client
-----------------

.. php:class:: Omeka_Http_Client

    Wrapper for Zend_Http_Client.
    
    Adds the following functionality: retries on timeouts.

    .. php:attr:: _maxRetries
    


    .. php:attr:: _retryCount
    


    .. php:method:: request($method)
    
        Wraps Zend_Http_Client to automatically retry timed out requests.
        
        :param unknown $method:

    .. php:method:: setMaxRetries(integer $count)
    
        Set the maximum number of retries to make when a request times out.
        
        :param integer $count: