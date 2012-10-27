-----------------
Omeka_Application
-----------------

.. php:class:: Omeka_Application

    Package: :doc:`Application </Reference/packages/Application/index>`

    Core class used to bootstrap the Omeka environment.
    
    Various duties include, but are not limited to setting up class autoload, 
    database, configuration files, logging, plugins, front controller, etc.
    
    When any core resource returns from init(), the result is stored in thebootstrap container. Other parts of the application can get the resourcesfrom the bootstrap when needed.

    .. php:method:: __construct(string $environment, string|array|Zend_Config $options)
    
        Initialize the application.
        
        :param string $environment: The environment name.
        :param string|array|Zend_Config $options: Application configuration.

    .. php:method:: initialize()
    
        Bootstrap the entire application.

    .. php:method:: run()
    
        Display the generic error page for all otherwise-uncaught exceptions.

    .. php:method:: _displayErrorPage(Exception $e, string $title)
    
        Print an HTML page to display errors when starting the application.
        
        :param Exception $e: 
        :param string $title: The title of the error page.