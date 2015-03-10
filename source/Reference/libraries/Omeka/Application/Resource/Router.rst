---------------------------------
Omeka_Application_Resource_Router
---------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Router

extends :php:class:`Zend_Application_Resource_Router`

    Set up the router and the built-in routes.

    .. php:method:: init()

        :returns: Zend_Controller_Router_Rewrite

    .. php:method:: _addHomepageRoute($router)

        Adds the homepage route to the router (as specified by the navigation
        settings page)
        The route will not be added if the user is currently on the admin theme.

        :type $router: Zend_Controller_Router_Rewrite
        :param $router: The router

    .. php:method:: _addHomepageRedirect($uri, $router)

        Adds a redirect route for the homepage.

        A redirect is required to make a "homepage" that is an external URL, an
        admin URL, or a URL with a query string.

        :type $uri: string
        :param $uri: The absolute uri to redirect to the default route to
        :type $router: Zend_Controller_Router_Rewrite
        :param $router: The router
        :returns: boolean True if the route was successfully added, else false.

    .. php:method:: _leftTrim($s, $n)

        Left trims the first occurrence of a string within a string.
        Note: it will only trim the first occurrence of the string.

        :type $s: string
        :param $s: The base string
        :type $n: string
        :param $n: The string to remove from the left side of the base string
        :returns: string
