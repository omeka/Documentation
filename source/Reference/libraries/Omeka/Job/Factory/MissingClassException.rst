---------------------------------------
Omeka_Job_Factory_MissingClassException
---------------------------------------

Package: :doc:`Job\\Factory </Reference/packages/Job/Factory/index>`

.. php:class:: Omeka_Job_Factory_MissingClassException

extends :php:class:`InvalidArgumentException`

implements :php:interface:`Throwable`

    Exception thrown when the type of job could not be inferred from the message
    passed to the factory.

    .. php:attr:: message

        protected

    .. php:attr:: code

        protected

    .. php:attr:: file

        protected

    .. php:attr:: line

        protected

    .. php:method:: __clone()

    .. php:method:: __construct($message, $code, $previous)

        :param $message:
        :param $code:
        :param $previous:

    .. php:method:: __wakeup()

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()
