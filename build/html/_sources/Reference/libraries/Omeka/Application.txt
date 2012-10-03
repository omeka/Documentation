-----------------
Omeka_Application
-----------------

.. php:class:: Omeka_Application

    Core class used to bootstrap the Omeka environment.
    
    Various duties include, but are not limited to, sanitizing magic_quotes,
    setting up class autoload, database, configuration files, logging, plugins,
    front controller, etc.
    
    When any core resource returns from init(), the result is stored in the bootstrap container. Other parts of the application can get the resources from the bootstrap when needed.

    .. php:method:: __construct(string $environment, string|array|Zend_Config $options)
    
        Initialize the application.
        
        :param string $environment: Environment name.
        :param string|array|Zend_Config $options: Application configuration.

    .. php:method:: initialize()
    
        Bootstrap the entire application.
        
        This will initialize all the elements of the application.
        
        :returns: void

    .. php:method:: sanitizeMagicQuotes()
    
        If magic_quotes has been enabled, then strip all slashes from the $_GET, 
        $_POST and $_REQUEST superglobals.
        
        :returns: void

    .. php:method:: run()
    
        Display the generic error page for all otherwise-uncaught exceptions.

    .. php:method:: _displayErrorPage(Exception $e, $title)
    
        Print an HTML page to display errors when starting the application.
        
        :param Exception $e: 
        :param unknown $title: 
        :returns: void

    .. php:method:: _stripSlashes(mixed $value)
    
        Strip slashes.
        
        Filters request superglobals in order to avoid problems with PHP's magic_quotes setting.
        
        :param mixed $value: 
        :returns: mixed

