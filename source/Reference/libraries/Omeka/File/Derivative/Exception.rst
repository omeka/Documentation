-------------------------------
Omeka_File_Derivative_Exception
-------------------------------

Package: :doc:`File\\Derivative </Reference/packages/File/Derivative/index>`

.. php:class:: Omeka_File_Derivative_Exception

extends :php:class:`Exception`

    Exception to throw when something goes wrong in the process of creating
    derivative images.

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
