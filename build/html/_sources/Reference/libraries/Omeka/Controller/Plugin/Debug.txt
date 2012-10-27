-----------------------------
Omeka_Controller_Plugin_Debug
-----------------------------

.. php:class:: Omeka_Controller_Plugin_Debug

    Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

    This controller plugin allows for debugging Request objects without inserting 
    debugging code into the Zend Framework code files.
    
    Debugging web requests is enabled by setting 'debug.request = true' in theconfig.ini file.

    .. php:attr:: _requestMarkup
    


    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)
    
        Print request debugging info for every request.
        
        Has no effect if request debugging is not enabled in config.ini.
        
        :param Zend_Controller_Request_Abstract $request: Request object.
        :returns: void

    .. php:method:: postDispatch(Zend_Controller_Request_Abstract $request)
    
        :param Zend_Controller_Request_Abstract $request:

    .. php:method:: dispatchLoopShutdown()
    
        Print database profiling info.
        
        Enabled conditionally when debug.profileDb = true in config.ini.
        
        :returns: void

    .. php:method:: _getProfilerMarkup(Zend_Db_Profiler $profiler)
    
        :param Zend_Db_Profiler $profiler:

    .. php:method:: _getRequestMarkup(Zend_Controller_Request_Abstract $request, Zend_Controller_Router_Interface $router)
    
        Create HTML markup for request debugging.
        
        :param Zend_Controller_Request_Abstract $request: Request object.
        :param Zend_Controller_Router_Interface $router: Router object.
        :returns: string HTML markup.