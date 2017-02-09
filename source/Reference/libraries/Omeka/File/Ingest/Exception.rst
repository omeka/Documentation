---------------------------
Omeka_File_Ingest_Exception
---------------------------

Package: :doc:`File\\Ingest </Reference/packages/File/Ingest/index>`

.. php:class:: Omeka_File_Ingest_Exception

extends :php:class:`Exception`

implements :php:interface:`Throwable`

    An exception to be thrown when something goes wrong during the file ingest
    process.

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
