-----------------
UpgradeController
-----------------

.. php:class:: UpgradeController

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    .. php:method:: __construct(Zend_Controller_Request_Abstract $request, Zend_Controller_Response_Abstract $response, $invokeArgs = Array)
    
        :param Zend_Controller_Request_Abstract $request: 
        :param Zend_Controller_Response_Abstract $response: 
        :param unknown $invokeArgs:

    .. php:method:: indexAction()

    .. php:method:: migrateAction()
    
        Run the migration script, obtain any success/error output and display it in a pretty way
        
        :returns: void