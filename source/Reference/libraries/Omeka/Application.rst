-----------------
Omeka_Application
-----------------

Package: :doc:`Application </Reference/packages/Application/index>`

.. php:class:: Omeka_Application

extends :php:class:`Zend_Application`

    Core class used to bootstrap the Omeka environment.

    Various duties include, but are not limited to setting up class autoload,
    database, configuration files, logging, plugins, front controller, etc.

    When any core resource returns from init(), the result is stored in the bootstrap container. Other parts of the application can get the resources from the bootstrap when needed.

    .. php:method:: __construct($environment, $options = null)

        Initialize the application.

        :type $environment: string
        :param $environment: The environment name.
        :type $options: string|array|Zend_Config
        :param $options: Application configuration.

    .. php:method:: initialize()

        Bootstrap the entire application.

    .. php:method:: run()

        Display the generic error page for all otherwise-uncaught exceptions.

    .. php:method:: _displayErrorPage($e, $title = null)

        Print an HTML page to display errors when starting the application.

        :type $e: Exception
        :param $e:
        :type $title: string
        :param $title: The title of the error page.
