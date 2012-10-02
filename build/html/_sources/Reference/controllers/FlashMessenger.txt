---------------------------------------------
Omeka_Controller_Action_Helper_FlashMessenger
---------------------------------------------

.. php:class:: Omeka_Controller_Action_Helper_FlashMessenger

    FlashMessenger action helper.

    .. php:attr:: _messenger
    


    .. php:method:: __construct()

    .. php:method:: addMessage($message, $status)
    
        addMessage() - Add a message to flash message
        
        :param unknown $message: 
        :param unknown $status: 
        :returns: Mu_Controller_Action_Helper_FlashMessenger Provides a fluent interface

    .. php:method:: getMessages()
    
        getMessages() - Get messages
        
        :returns: array

    .. php:method:: _filterMessages($messages)
    
        :param unknown $messages:

    .. php:method:: clearMessages()
    
        Clear all messages from the previous request & specified status
        
        :returns: boolean True if messages were cleared, false if none existed

    .. php:method:: clearCurrentMessages()
    
        Clear all current messages with specified status
        
        :returns: boolean True if messages were cleared, false if none existed

    .. php:method:: hasMessages()
    
        Whether has messages with a specific status (or any messages, if null).

    .. php:method:: hasCurrentMessages()

    .. php:method:: getCurrentMessages($status)
    
        :param unknown $status:

    .. php:method:: direct($message, $status)
    
        Strategy pattern: proxy to addMessage()
        
        :param unknown $message: 
        :param unknown $status: 
        :returns: void

