----------------------------
Omeka_Job_Dispatcher_Default
----------------------------

Package: :doc:`Job\\Dispatcher </Reference/packages/Job/Dispatcher/index>`

.. php:class:: Omeka_Job_Dispatcher_Default

implements :php:interface:`Omeka_Job_Dispatcher_DispatcherInterface`

    Dispatches jobs in Omeka.

    This provides a clean interface to adapter classes that deal with the details of how to dispatch jobs. It is initialized in the Jobs bootstrap resource and can be accessed via the registry.

    Standard usage, where Job_Class_Name corresponds to a valid class name for a class implementing Omeka_JobInterface:

    <code>
    $dispatcher = Zend_Registry::get('job_dispatcher');
    $dispatcher->send('Job_Class_Name', array(
         'firstOption' => 'text',
         'secondOption' => 2
    ));
    </code>

    .. php:method:: __construct(Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter, Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter, $user)

        :type $defaultAdapter: Omeka_Job_Dispatcher_Adapter_AdapterInterface
        :param $defaultAdapter:
        :type $longRunningAdapter: Omeka_Job_Dispatcher_Adapter_AdapterInterface
        :param $longRunningAdapter:
        :type $user: User|null
        :param $user: The user account associated with the request, i.e. the user account associated with jobs sent by the dispatcher.

    .. php:method:: setUser($user)

        Set the user.

        :type $user: User|null
        :param $user:

    .. php:method:: getUser()

        Get the user.

        :returns: User|null

    .. php:method:: setDefaultAdapter(Omeka_Job_Dispatcher_Adapter_AdapterInterface $defaultAdapter)

        Set the default adapter.

        :type $defaultAdapter: Omeka_Job_Dispatcher_Adapter_AdapterInterface
        :param $defaultAdapter:

    .. php:method:: setLongRunningAdapter(Omeka_Job_Dispatcher_Adapter_AdapterInterface $longRunningAdapter)

        Set the long running adapter.

        :type $longRunningAdapter: Omeka_Job_Dispatcher_Adapter_AdapterInterface
        :param $longRunningAdapter:

    .. php:method:: setQueueName($name)

        Set the name of the queue to which default jobs will be sent.

        NOTE: This may be ignored by adapters that do not understand the notion of
        named queues (or queues in general).

        :type $name: string
        :param $name:

    .. php:method:: setQueueNameLongRunning($name)

        Set the name of the queue to which long-running jobs will be sent.

        NOTE: This may be ignored by adapters that do not understand the notion of
        named queues (or queues in general).

        :type $name: string
        :param $name:

    .. php:method:: send($jobClass, $options = array())

        Dispatch a job using the default dispatcher.

        :type $jobClass: string
        :param $jobClass: Class name that implements Omeka_JobInterface.
        :type $options: array
        :param $options: Optional associative array containing options that the task needs in order to do its job. Note that all options should be primitive data types (or arrays containing primitive data types).

    .. php:method:: sendLongRunning($jobClass, $options = array())

        Dispatch a job using the long-running dispatcher.

        :type $jobClass: string
        :param $jobClass: Name of a class that implements Omeka_JobInterface.
        :type $options: array
        :param $options: Optional associative array containing options that the task needs in order to do its job. Note that all options should be primitive data types (or arrays containing primitive data types).

    .. php:method:: _getJobMetadata($class, $options)

        :param $class:
        :param $options:

    .. php:method:: _toJson($metadata)

        :param $metadata:
