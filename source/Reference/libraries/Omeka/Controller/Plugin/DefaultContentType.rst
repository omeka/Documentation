------------------------------------------
Omeka_Controller_Plugin_DefaultContentType
------------------------------------------

.. php:class:: Omeka_Controller_Plugin_DefaultContentType

    This controller plugin sets the default Content-Type header when one hasn't
    been set at the end of the controller processing.
    
    This has to be done here because Zend allows header duplication, theoutput contexts don't overwrite headers of the same name, and some servers(FastCGI) choke when they see two Content-Type headers.

    .. php:method:: dispatchLoopShutdown()
    
        Add a default Content-Type to the response if none is already set.