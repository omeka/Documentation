----------------------------------------
Omeka_Job_Dispatcher_DispatcherInterface
----------------------------------------

.. php:class:: Omeka_Job_Dispatcher_DispatcherInterface

    Package: :doc:`/Reference/packages/Job\Dispatcher/index`

    Interface for job dispatchers in Omeka.

    .. php:method:: setQueueName(string $name)
    
        Set the name of the queue to which jobs will be sent.
        
        NOTE: This may be ignored by adapters that do not understand the notionof named queues (or queues in general).
        
        :param string $name:

    .. php:method:: send(string $jobClass, array $options = Array)
    
        :param string $jobClass: Name of a class that implements Omeka_JobInterface.
        :param array $options: Optional Associative array containing options that the task needs in order to do its job.  Note that all options should be primitive data types (or arrays containing primitive data types).