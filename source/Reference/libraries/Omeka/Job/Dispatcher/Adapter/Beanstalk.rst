--------------------------------------
Omeka_Job_Dispatcher_Adapter_Beanstalk
--------------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_Beanstalk

    Job dispatcher for Beanstalk.
    
    Requires Pheanstalk library (Beanstalk client) in order to work properly.
    
    This adapter must be instantiated with the 'host' option (IP address of beanstalk daemon) in order to work properly.

    .. php:const:: DEFAULT_TTR
    
    
    
        Because of the potential for long-running imports (and the fact that 
        jobs are not idemopotent), TTR should be pretty high by default.

    .. php:attr:: _pheanstalk
    


    .. php:attr:: _options
    


    .. php:method:: setQueueName(string $name)
    
        Beanstalk understands the concept of 'tubes' instead of named queues, so 
        set the appropriate 'tube' to dispatch jobs.
        
        :param string $name:

    .. php:method:: send($encodedJob, $metadata)
    
        :param unknown $encodedJob: 
        :param unknown $metadata:

    .. php:method:: _pheanstalk()

    .. php:method:: getOption($name)
    
        :param unknown $name:

    .. php:method:: __construct(array|null $options)
    
        :param array|null $options: Optional Options to instantiate in the adapter.

    .. php:method:: _setOptions($options)
    
        :param unknown $options:

    .. php:method:: hasOption(string $name)
    
        Whether or not the given option has been set.
        
        :param string $name: