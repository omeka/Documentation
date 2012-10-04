-------------------------------
Omeka_Controller_Plugin_Upgrade
-------------------------------

.. php:class:: Omeka_Controller_Plugin_Upgrade

    Overrides Omeka's normal routing when the database needs to be upgraded.

    .. php:method:: dispatchLoopStartup(Zend_Controller_Request_Abstract $request)
    
        Set up routing for the upgrade controller.
        
        Only allows authorized users to upgrade, and blocks the public site when an upgrade is needed.
        
        :param Zend_Controller_Request_Abstract $request: Request object.
        :returns: void

    .. php:method:: _dbNeedsUpgrade()

    .. php:method:: _dbCanUpgrade()

    .. php:method:: _upgrade(Zend_Controller_Request_Abstract $request)
    
        Redirect to the upgrade controller.
        
        :param Zend_Controller_Request_Abstract $request: Request object (not used).
        :returns: void