---------------------------------------------
Omeka_Controller_Action_Helper_FlashMessenger
---------------------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_FlashMessenger

extends :php:class:`Zend_Controller_Action_Helper_Abstract`

    FlashMessenger action helper.

    .. php:method:: __construct()

    .. php:method:: addMessage($message, $status = null)

        addMessage() - Add a message to flash message

        :param $message:
        :param $status:
        :returns: Mu_Controller_Action_Helper_FlashMessenger Provides a fluent interface

    .. php:method:: getMessages()

        getMessages() - Get messages

        :returns: array

    .. php:method:: _filterMessages($messages)

        :param $messages:

    .. php:method:: clearMessages()

        Clear all messages from the previous request & specified status

        :returns: bool True if messages were cleared, false if none existed

    .. php:method:: clearCurrentMessages()

        Clear all current messages with specified status

        :returns: bool True if messages were cleared, false if none existed

    .. php:method:: hasMessages()

        Whether has messages with a specific status (or any messages, if null).

    .. php:method:: hasCurrentMessages()

    .. php:method:: getCurrentMessages($status = null)

        :param $status:

    .. php:method:: direct($message, $status = null)

        Strategy pattern: proxy to addMessage()

        :param $message:
        :param $status:
