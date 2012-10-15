-----------------------------
Omeka_Controller_Plugin_Admin
-----------------------------

.. php:class:: Omeka_Controller_Plugin_Admin

    This controller plugin allows for all functionality that is specific to the 
    Admin theme.
    
    For now, all this includes is preventing unauthenticated access to all adminpages, with the exception of a few white-listed URLs, which are stored inthis plugin.
    
    This controller plugin should be loaded only in the admin bootstrap.

    .. php:attr:: _adminWhitelist
    
        Controller/Action list for admin actions that do not require being logged-in

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)
    
        Direct requests to the admin interface.
        Called upon router startup, before the request is routed.
        
        :param Zend_Controller_Request_Abstract $request: 
        :returns: void

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)
    
        Require login when attempting to access the admin interface.
        Whitelisted controller/action combinations are exempt from this
        requirement.
        Called before dispatching.
        
        :param Zend_Controller_Request_Abstract $request: 
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
        
        :param unknown $request: 
        :returns: boolean