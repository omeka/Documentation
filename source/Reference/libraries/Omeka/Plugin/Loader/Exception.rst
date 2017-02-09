-----------------------------
Omeka_Plugin_Loader_Exception
-----------------------------

Package: :doc:`Plugin\\Loader </Reference/packages/Plugin/Loader/index>`

.. php:class:: Omeka_Plugin_Loader_Exception

extends :php:class:`Exception`

implements :php:interface:`Throwable`

    An exception thrown when the plugin loader is unable to load a plugin.

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
