------------------------------
Omeka_Controller_Exception_404
------------------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: Omeka_Controller_Exception_404

extends :php:class:`Exception`

    If thrown within a controller, this will be caught in the ErrorController,
    which will render a 404 Not Found page.

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
