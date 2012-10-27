-----------------------
Omeka_View_Helper_Flash
-----------------------

.. php:class:: Omeka_View_Helper_Flash

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    View helper to display messages from FlashMessenger.

    .. php:attr:: _flashMessenger
    


    .. php:method:: __construct()

    .. php:method:: flash()
    
        Display messages from the FlashMessenger.
        
        :returns: string HTML for messages.

    .. php:method:: _getListHtml(string $status, string $message)
    
        Get the HTML for a message.
        
        :param string $status: 
        :param string $message: 
        :returns: string