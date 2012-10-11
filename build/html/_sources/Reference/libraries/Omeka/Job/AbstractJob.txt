---------------------
Omeka_Job_AbstractJob
---------------------

.. php:class:: Omeka_Job_AbstractJob

    Abstract implementation of an Omeka job.
    
    Most plugin implementations of jobs will extend this class to gainconvenient access to the database and other potentially importantresources.
    
    For information on how to dispatch jobs, see Omeka_Job_Dispatcher_DispatcherInterface.

    .. php:attr:: _db
    


    .. php:attr:: _dispatcher
    


    .. php:attr:: _user
    


    .. php:attr:: _options
    


    .. php:method:: __construct($options)
    
        :param unknown $options:

    .. php:method:: _setOptions($options)
    
        Set all the options associated with this task.
        
        This is a convenience method that calls setter methods for the optionsgiven in the array.  If an element in the
        array does not have anassociated setter method, it will be passed into the options array.
        
        :param unknown $options:

    .. php:method:: setDb(Omeka_Db $db)
    
        :param Omeka_Db $db:

    .. php:method:: setJobDispatcher(Omeka_Job_Dispatcher_DispatcherInterface $dispatcher)
    
        :param Omeka_Job_Dispatcher_DispatcherInterface $dispatcher:

    .. php:method:: setUser(User $user)
    
        Set the given User object on the Job object.
        
        :param User $user:

    .. php:method:: getUser()
    
        Get the User currently set on this Job, if any.
        
        :returns: User|null

    .. php:method:: resend()
    
        Resend the job using the same options that were passed to the current 
        job.

    .. php:method:: perform()