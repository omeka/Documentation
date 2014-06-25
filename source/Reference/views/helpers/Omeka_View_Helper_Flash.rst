-----------------------
Omeka_View_Helper_Flash
-----------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_Flash

extends :php:class:`Zend_View_Helper_Abstract`

    View helper to display messages from FlashMessenger.

    .. php:method:: __construct()

    .. php:method:: flash()

        Display messages from the FlashMessenger.

        :returns: string HTML for messages.

    .. php:method:: _getListHtml($status, $message)

        Get the HTML for a message.

        :type $status: string
        :param $status:
        :type $message: string
        :param $message:
        :returns: string
