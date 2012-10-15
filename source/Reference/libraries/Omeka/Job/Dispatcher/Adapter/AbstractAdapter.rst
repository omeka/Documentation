--------------------------------------------
Omeka_Job_Dispatcher_Adapter_AbstractAdapter
--------------------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_AbstractAdapter

    Package: Job\Dispatcher\Adapter

    Abstract class for job dispatcher adapters.

    .. php:attr:: _options
    


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

    .. php:method:: send(string $encodedJob, array $metadata)
    
        Send the job to whatever underlying system is used by the adapter.
        
        :param string $encodedJob: The job encoded as a string.  In most cases, this will be passed directly into whatever client or queue the adapter uses.
        :param array $metadata: An array containing all the metadata for the job. This is the unencoded version of the first argument and exists as a convenience so that adapter writers do not have to attempt to decode the first argument manually. This array contains the following keys: <ul> <li>className - Corresponds to the class name of the job.</li> <li>options - Options that are passed to the job when it is instantiated.</li> <li>createdBy - User object (or null) corresponding to the user who created this job.</li> <li>createdAt - Zend_Date corresponding to the date/time at which this job was created.</li> </ul>