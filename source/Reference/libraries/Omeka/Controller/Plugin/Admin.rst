-----------------------------
Omeka_Controller_Plugin_Admin
-----------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_Admin

extends :php:class:`Zend_Controller_Plugin_Abstract`

    This controller plugin allows for all functionality that is specific to the
    Admin theme.

    For now, all this includes is preventing unauthenticated access to all admin pages, with the exception of a few white-listed URLs, which are stored in this plugin.

    This controller plugin should be loaded only in the admin bootstrap.

    .. php:attr:: _adminWhitelist

        protected string

        Controller/Action list for admin actions that do not require being
        logged-in

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)

        Direct requests to the admin interface.
        Called upon router startup, before the request is routed.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :returns: void

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)

        Require login when attempting to access the admin interface.
        Whitelisted controller/action combinations are exempt from this
        requirement.
        Called before dispatching.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :returns: void

    .. php:method:: getRedirector()

        Return the redirector action helper.

        :returns: Zend_Controller_Action_Helper_Redirector

    .. php:method:: getAuth()

        Return the auth object.

        :returns: Zend_Auth

    .. php:method:: _requireLogin($request)

        Determine whether or not the request requires an authenticated
        user.

        :param $request:
        :returns: boolean
