----------------------------
Omeka_Job_Dispatcher_Default
----------------------------

.. php:class:: Omeka_Job_Dispatcher_Default

    Package: :doc:`Job\\Dispatcher </Reference/packages/Job/Dispatcher/index>`

    Dispatches jobs in Omeka.
    
    This provides a clean interface to adapter classes that deal with the detailsof how to dispatch jobs. It is initialized in the Jobs bootstrap resource andcan be accessed via the registry.
    
    Standard usage, where Job_Class_Name corresponds to a valid class name for a class implementing Omeka_JobInterface:
    
    	               
    
        .. code-block:: php 
    
    
    	               $dispatcher = Zend_Registry::get('job_dispatcher');
    	               $dispatcher->send('Job_Class_Name', array(
    	                    'firstOption' => 'text',
    	                    'secondOption' => 2
    	               ));

    .. php:attr:: _defaultAdapter
    


    .. php:attr:: _longRunningAdapter
    


    .. php:attr:: _user
    


    .. php:method:: __construct(Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter, Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter, User|null $user)
    
        :param Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter: 
        :param Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter: 
        :param User|null $user: The user account associated with the request, i.e. the user account associated with jobs sent by the dispatcher.

    .. php:method:: setUser(User|null $user)
    
        Set the user.
        
        :param User|null $user:

    .. php:method:: getUser()
    
        Get the user.
        
        :returns: User|null

    .. php:method:: setDefaultAdapter(Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter)
    
        Set the default adapter.
        
        :param Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter:

    .. php:method:: setLongRunningAdapter(Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter)
    
        Set the long running adapter.
        
        :param Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter:

    .. php:method:: setQueueName(string $name)
    
        Set the name of the queue to which default jobs will be sent.
        
        NOTE: This may be ignored by adapters that do not understand the notionof named queues (or queues in general).
        
        :param string $name:

    .. php:method:: setQueueNameLongRunning(string $name)
    
        Set the name of the queue to which long-running jobs will be sent.
        
        NOTE: This may be ignored by adapters that do not understand the notionof named queues (or queues in general).
        
        :param string $name:

    .. php:method:: send(string $jobClass, array $options)
    
        Dispatch a job using the default dispatcher.
        
        :param string $jobClass: Class name that implements Omeka_JobInterface.
        :param array $options: Optional associative array containing options that the task needs in order to do its job. Note that all options should be primitive data types (or arrays containing primitive data types).

    .. php:method:: sendLongRunning(string $jobClass, array $options)
    
        Dispatch a job using the long-running dispatcher.
        
        :param string $jobClass: Name of a class that implements Omeka_JobInterface.
        :param array $options: Optional associative array containing options that the task needs in order to do its job. Note that all options should be primitive data types (or arrays containing primitive data types).

    .. php:method:: _getJobMetadata($class, $options)
    
        :param unknown $class: 
        :param unknown $options:

    .. php:method:: _toJson($metadata)
    
        :param unknown $metadata: