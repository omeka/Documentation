-----------------
UpgradeController
-----------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: UpgradeController

extends :php:class:`Zend_Controller_Action`

    .. php:method:: __construct(Zend_Controller_Request_Abstract $request, Zend_Controller_Response_Abstract $response, $invokeArgs = array())

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :type $response: Zend_Controller_Response_Abstract
        :param $response:
        :param $invokeArgs:

    .. php:method:: indexAction()

    .. php:method:: migrateAction()

        Run the migration script, obtain any success/error output and display it
        in a pretty way

        :returns: void
