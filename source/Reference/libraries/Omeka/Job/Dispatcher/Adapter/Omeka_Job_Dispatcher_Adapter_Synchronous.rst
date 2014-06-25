----------------------------------------
Omeka_Job_Dispatcher_Adapter_Synchronous
----------------------------------------

Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

.. php:class:: Omeka_Job_Dispatcher_Adapter_Synchronous

extends :php:class:`Omeka_Job_Dispatcher_Adapter_AbstractAdapter`

implements :php:interface:`Omeka_Job_Dispatcher_Adapter_AdapterInterface`

    Dispatcher for executing jobs in real-time, i.e. executing within the browser
    request.

    WARNING: While especially useful for simple jobs or instances where it is not possible to use one of the other adapters, keep in mind that long jobs may lead to request timeouts or open the possibility of DoS attacks by malicious users.

    .. php:method:: send($encodedJob, $metadata)

        :param $encodedJob:
        :param $metadata:

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
