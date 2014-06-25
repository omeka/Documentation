---------------------------
Omeka_Controller_Plugin_Ssl
---------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_Ssl

extends :php:class:`Zend_Controller_Plugin_Abstract`

    Handle SSL configuration for Omeka sites.

    .. php:method:: __construct($sslConfig, $redirector, Zend_Auth $auth)

        :param $sslConfig:
        :param $redirector:
        :type $auth: Zend_Auth
        :param $auth:

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)

        :type $request: Zend_Controller_Request_Abstract
        :param $request:

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)

        :type $request: Zend_Controller_Request_Abstract
        :param $request:

    .. php:method:: _isLoginRequest($request)

        :param $request:

    .. php:method:: _secureAuthenticatedSession()

        Unauthenticated sessions are not as valuable to attackers, so we only
        really need to check if an authenticated session is being used.

    .. php:method:: _isSslRequest($request)

        :param $request:

    .. php:method:: _redirect($request)

        :param $request:

    .. php:method:: _secureAllRequests()
