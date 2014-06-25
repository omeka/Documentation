--------------------------------------
Omeka_Job_Dispatcher_Adapter_Beanstalk
--------------------------------------

Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

.. php:class:: Omeka_Job_Dispatcher_Adapter_Beanstalk

extends :php:class:`Omeka_Job_Dispatcher_Adapter_AbstractAdapter`

implements :php:interface:`Omeka_Job_Dispatcher_Adapter_AdapterInterface`

    Job dispatcher for Beanstalk.

    Requires Pheanstalk library (Beanstalk client) in order to work properly.

    This adapter must be instantiated with the 'host' option (IP address of beanstalk daemon) in order to work properly.

    .. php:const:: DEFAULT_TTR

        Because of the potential for long-running imports (and the fact that
        jobs are not idemopotent), TTR should be pretty high by default.

    .. php:method:: setQueueName($name)

        Beanstalk understands the concept of 'tubes' instead of named queues, so
        set the appropriate 'tube' to dispatch jobs.

        :type $name: string
        :param $name:

    .. php:method:: send($encodedJob, $metadata)

        :param $encodedJob:
        :param $metadata:

    .. php:method:: _pheanstalk()

    .. php:method:: getOption($name)

        :param $name:

    .. php:method:: __construct($options = null)

        :type $options: array|null
        :param $options: Optional Options to instantiate in the adapter.

    .. php:method:: _setOptions($options)

        :param $options:

    .. php:method:: hasOption($name)

        Whether or not the given option has been set.

        :type $name: string
        :param $name:
