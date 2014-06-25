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

    .. php:method:: addRedirectRouteForDefaultRoute($routeName, $uri, $params = array(), $router = null)

        Adds a redirect route for the default route and returns whether the route
        was successfully added
        If the current request matches the default route, then the flow will
        redirect to the
        index action of the RedirectorController, where the page will be
        redirected to the absolute uri
        We must use this Redirector proxy controller because a user may be
        redirecting to an admin page and it needs
        to reload the application from the admin context.  Also, the Zend router
        and dispatcher
        does not allow us to directly dispatch to an absolute uri.

        :type $routeName: String
        :param $routeName: The name of the new redirect route
        :type $uri: String
        :param $uri: The absolute uri to redirect to the default route to
        :type $params: array
        :param $params: The parameters for the redirect route.
        :type $router: Zend_Controller_Router_Rewrite
        :param $router: The router
        :returns: boolean Returns true if the route was successfully added, else false.

    .. php:method:: _leftTrim($s, $n)

        Left trims the first occurrence of a string within a string.
        Note: it will only trim the first occurrence of the string.

        :type $s: string
        :param $s: The base string
        :type $n: string
        :param $n: The string to remove from the left side of the base string
        :returns: string
