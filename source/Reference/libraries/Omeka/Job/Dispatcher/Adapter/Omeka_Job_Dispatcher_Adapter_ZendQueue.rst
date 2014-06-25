--------------------------------------
Omeka_Job_Dispatcher_Adapter_ZendQueue
--------------------------------------

Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

.. php:class:: Omeka_Job_Dispatcher_Adapter_ZendQueue

extends :php:class:`Omeka_Job_Dispatcher_Adapter_AbstractAdapter`

implements :php:interface:`Omeka_Job_Dispatcher_Adapter_AdapterInterface`

    Dispatcher for Zend_Queue.

    This would be particularly useful for installations that want to interface with ActiveMQ or Zend Server's Job Queue via Zend_Queue.  Note that using the 'Array' adapter should only be used for testing, as all jobs passed to it will be thrown away.

    Required options include 'adapter' and 'options', which correspond to the first and second arguments to Zend_Queue's constructor respectively.

    For example, it would be configured like so in config.ini:
    <code>
    jobs.dispatcher = "Omeka_Job_Dispatcher_ZendQueue"
    jobs.adapterOptions.adapter = "PlatformJobQueue"
    jobs.adapterOptions.options.host = "127.0.0.1"
    jobs.adapterOptions.options.password = "foobar"
    </code>

    .. php:method:: setQueueName($name)

        Note that some Zend_Queue implementations understand the concept of
        named queues, while others do not.

        :param $name:

    .. php:method:: send($encodedJob, $metadata)

        :param $encodedJob:
        :param $metadata:

    .. php:method:: _queue()

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
