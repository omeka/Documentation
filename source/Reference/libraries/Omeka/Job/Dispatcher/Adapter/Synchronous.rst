----------------------------------------
Omeka_Job_Dispatcher_Adapter_Synchronous
----------------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_Synchronous

    Dispatcher for executing jobs in real-time, i.e. executing within the 
    browser request.
    
    WARNING: While especially useful for simple jobs or instances where it is not possible to use one of the other adapters, keep in mind that long jobs may lead to request timeouts or open the possibility of DoS attacks by malicious users.

    .. php:attr:: _options
    


    .. php:method:: send($encodedJob, $metadata)
    
        :param unknown $encodedJob: 
        :param unknown $metadata:

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

    .. php:method:: setQueueName($name)
    
        Adapter implementations do not understand named queues by default, so 
        this default implementation returns false.  Override this in subclasses 
        to specify the correct behavior.
        
        :param unknown $name: