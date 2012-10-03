--------------------------------------
Omeka_Job_Dispatcher_Adapter_ZendQueue
--------------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_ZendQueue

    Dispatcher for Zend_Queue.
    
    This would be particularly useful for installations that want to interface with ActiveMQ or Zend Server's Job Queue via Zend_Queue.  Note that using the 'Array' adapter should only be used for testing, as all jobs passed to it will be thrown away. 
    
    Required options include 'adapter' and 'options', which correspond to the first and second arguments to Zend_Queue's constructor respectively.
    
    For example, it would be configured like so in config.ini:
        .. code-block:: php 
    
         jobs.dispatcher = "Omeka_Job_Dispatcher_ZendQueue"
         jobs.adapterOptions.adapter = "PlatformJobQueue"
         jobs.adapterOptions.options.host = "127.0.0.1"
         jobs.adapterOptions.options.password = "foobar"

    .. php:attr:: _queue
    


    .. php:attr:: _options
    


    .. php:method:: setQueueName($name)
    
        Note that some Zend_Queue implementations understand the concept of 
        named queues, while others do not.
        
        :param unknown $name:

    .. php:method:: send($encodedJob, $metadata)
    
        :param unknown $encodedJob: 
        :param unknown $metadata:

    .. php:method:: _queue()

    .. php:method:: __construct(array|null $options)
    
        :param array|null $options: Optional Options to instantiate in the adapter.

    .. php:method:: _setOptions($options)
    
        :param unknown $options:

    .. php:method:: getOption(string $name)
    
        Retrieve an option by name as it was passed to the constructor of the 
        adapter.
        
        :param string $name:

    .. php:method:: hasOption(string $name)
    
        Whether or not the given option has been set.
        
        :param string $name:

