------------------------
Omeka_Validate_Exception
------------------------

Package: :doc:`Validate </Reference/packages/Validate/index>`

.. php:class:: Omeka_Validate_Exception

extends :php:class:`Exception`

implements :php:interface:`Throwable`

    Exception that is thrown when a form could not be validated correctly.

    .. php:attr:: _errors

        protected string

        Message representing form errors.

    .. php:attr:: message

        protected

    .. php:attr:: code

        protected

    .. php:attr:: file

        protected

    .. php:attr:: line

        protected

    .. php:method:: __construct($errors)

        :param $errors:
        :returns: void

    .. php:method:: getErrors()

        Get the error message that caused this exception.

        :returns: string

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
