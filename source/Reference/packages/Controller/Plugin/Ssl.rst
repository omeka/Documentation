---------------------------
Omeka_Controller_Plugin_Ssl
---------------------------

.. php:class:: Omeka_Controller_Plugin_Ssl

    Package: :doc:`/Reference/packages/Controller\Plugin/index`

    Handle SSL configuration for Omeka sites.

    .. php:attr:: _sslConfig
    


    .. php:attr:: _redirector
    


    .. php:attr:: _auth
    


    .. php:method:: __construct($sslConfig, $redirector, Zend_Auth $auth)
    
        :param unknown $sslConfig: 
        :param unknown $redirector: 
        :param Zend_Auth $auth:

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)
    
        :param Zend_Controller_Request_Abstract $request:

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)
    
        :param Zend_Controller_Request_Abstract $request:

    .. php:method:: _isLoginRequest($request)
    
        :param unknown $request:

    .. php:method:: _secureAuthenticatedSession()
    
        Unauthenticated sessions are not as valuable to attackers, so we only 
        really need to check if an authenticated session is being used.

    .. php:method:: _isSslRequest($request)
    
        :param unknown $request:

    .. php:method:: _redirect($request)
    
        :param unknown $request:

    .. php:method:: _secureAllRequests()