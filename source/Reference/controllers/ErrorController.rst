---------------
ErrorController
---------------

.. php:class:: ErrorController

    Handles all exceptions that are thrown in controllers.

    .. php:method:: errorAction()

    .. php:method:: _getException()

    .. php:method:: notFoundAction()
    
        Generic action to render a 404 page.
        
        :returns: void

    .. php:method:: forbiddenAction()

    .. php:method:: methodNotAllowedAction()

    .. php:method:: logException($e, $priority)
    
        :param unknown $e: 
        :param unknown $priority:

    .. php:method:: is404(Exception $e, $handler)
    
        Check to see whether the error qualifies as a 404 error
        
        :param Exception $e: 
        :param unknown $handler: 
        :returns: boolean

    .. php:method:: is403(Exception $e)
    
        :param Exception $e:

    .. php:method:: renderException(Exception $e)
    
        :param Exception $e:

    .. php:method:: isInDebugMode()

