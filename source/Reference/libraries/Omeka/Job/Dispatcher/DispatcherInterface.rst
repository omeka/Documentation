----------------------------------------
Omeka_Job_Dispatcher_DispatcherInterface
----------------------------------------

Package: :doc:`Job\\Dispatcher </Reference/packages/Job/Dispatcher/index>`

.. php:interface:: Omeka_Job_Dispatcher_DispatcherInterface

    Interface for job dispatchers in Omeka.

    .. php:method:: setQueueName($name)

        Set the name of the queue to which jobs will be sent.

        NOTE: This may be ignored by adapters that do not understand the notion of
        named queues (or queues in general).

        :type $name: string
        :param $name:

    .. php:method:: send($jobClass, $options = array())

        :type $jobClass: string
        :param $jobClass: Name of a class that implements Omeka_JobInterface.
        :type $options: array
        :param $options: Optional Associative array containing options that the task needs in order to do its job.  Note that all options should be primitive data types (or arrays containing primitive data types).
