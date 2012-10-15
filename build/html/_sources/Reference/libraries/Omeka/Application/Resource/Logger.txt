---------------------------------
Omeka_Application_Resource_Logger
---------------------------------

.. php:class:: Omeka_Application_Resource_Logger

    If logging has been enabled in the config file, then set up Zend's logging 
    mechanism.

    .. php:method:: init()
    
        :returns: Zend_Log

    .. php:method:: _addMailWriter(Zend_Log $log, string $toEmail, $filter)
    
        Set up debugging emails.
        
        :param Zend_Log $log: 
        :param string $toEmail: Email address of debug message recipient.
        :param unknown $filter: