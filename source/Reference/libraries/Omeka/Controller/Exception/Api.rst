------------------------------
Omeka_Controller_Exception_Api
------------------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: Omeka_Controller_Exception_Api

extends :php:class:`Exception`

implements :php:interface:`Throwable`

    API exception.

    API implementers should throw this exception for controller errors.

    .. php:attr:: _errors

        protected array

    .. php:attr:: message

        protected

    .. php:attr:: code

        protected

    .. php:attr:: file

        protected

    .. php:attr:: line

        protected

    .. php:method:: __construct($message, $code, $errors = array())

        :type $message: string
        :param $message:
        :type $code: int
        :param $code:
        :type $errors: array
        :param $errors: Custom errors

    .. php:method:: getErrors()

        :returns: array

    .. php:method:: __clone()

    .. php:method:: __wakeup()

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()
