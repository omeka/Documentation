----------------------------------------------
Omeka_Job_Dispatcher_Adapter_BackgroundProcess
----------------------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_BackgroundProcess

    Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

    Job dispatcher that uses Omeka's existing background process API.

    .. php:attr:: _processDispatcher
    


    .. php:attr:: _options
    


    .. php:method:: send($encodedJob, $metadata)
    
        Dispatches a background process that executes the given job.
        
        NOTE: No user account is bootstrapped when background.php runs (since itis CLI), so if a process triggers its own
        subprocesses, those will belisted as belonging to no user (ID = 0).
        
        :param unknown $encodedJob: 
        :param unknown $metadata:

    .. php:method:: setProcessDispatcher(Omeka_Job_Process_Dispatcher $dispatcher)
    
        For test purposes.
        
        :param Omeka_Job_Process_Dispatcher $dispatcher:

    .. php:method:: getProcessDispatcher()

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