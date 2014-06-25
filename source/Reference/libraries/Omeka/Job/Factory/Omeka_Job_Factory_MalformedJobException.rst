---------------------------------------
Omeka_Job_Factory_MalformedJobException
---------------------------------------

Package: :doc:`Job\\Factory </Reference/packages/Job/Factory/index>`

.. php:class:: Omeka_Job_Factory_MalformedJobException

extends :php:class:`InvalidArgumentException`

    Exception thrown when the message could not be decoded into valid job
    metadata.

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

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()
