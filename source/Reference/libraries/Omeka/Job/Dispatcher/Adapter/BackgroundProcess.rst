----------------------------------------------
Omeka_Job_Dispatcher_Adapter_BackgroundProcess
----------------------------------------------

Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

.. php:class:: Omeka_Job_Dispatcher_Adapter_BackgroundProcess

extends :php:class:`Omeka_Job_Dispatcher_Adapter_AbstractAdapter`

implements :php:interface:`Omeka_Job_Dispatcher_Adapter_AdapterInterface`

    Job dispatcher that uses Omeka's existing background process API.

    .. php:method:: send($encodedJob, $metadata)

        Dispatches a background process that executes the given job.

        NOTE: No user account is bootstrapped when background.php runs (since it
        is CLI), so if a process triggers its own subprocesses, those will be
        listed as belonging to no user (ID = 0).

        :param $encodedJob:
        :param $metadata:

    .. php:method:: setProcessDispatcher(Omeka_Job_Process_Dispatcher $dispatcher)

        For test purposes.

        :type $dispatcher: Omeka_Job_Process_Dispatcher
        :param $dispatcher:

    .. php:method:: getProcessDispatcher()

    .. php:method:: __construct($options = null)

        :type $options: array|null
        :param $options: Optional Options to instantiate in the adapter.

    .. php:method:: _setOptions($options)

        :param $options:

    .. php:method:: getOption($name)

        Retrieve an option by name as it was passed to the constructor of the
        adapter.

        :type $name: string
        :param $name:

    .. php:method:: hasOption($name)

        Whether or not the given option has been set.

        :type $name: string
        :param $name:

    .. php:method:: setQueueName($name)

        Adapter implementations do not understand named queues by default, so
        this default implementation returns false.  Override this in subclasses
        to specify the correct behavior.

        :param $name:
