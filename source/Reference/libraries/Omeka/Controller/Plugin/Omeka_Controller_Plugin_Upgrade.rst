-------------------------------
Omeka_Controller_Plugin_Upgrade
-------------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_Upgrade

extends :php:class:`Zend_Controller_Plugin_Abstract`

    Overrides Omeka's normal routing when the database needs to be upgraded.

    .. php:method:: dispatchLoopStartup(Zend_Controller_Request_Abstract $request)

        Set up routing for the upgrade controller.

        Only allows authorized users to upgrade, and blocks the public site when
        an upgrade is needed.

        :type $request: Zend_Controller_Request_Abstract
        :param $request: Request object.
        :returns: void

    .. php:method:: _dbNeedsUpgrade()

    .. php:method:: _dbCanUpgrade()

    .. php:method:: _upgrade($request)

        Redirect to the upgrade controller.

        :type $request: Zend_Controller_Request_Abstract
        :param $request: Request object (not used).
        :returns: void
