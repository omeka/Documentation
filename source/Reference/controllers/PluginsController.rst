-----------------
PluginsController
-----------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: PluginsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:method:: init()

    .. php:method:: configAction()

        Load the configuration form for a specific plugin.
        That configuration form will be POSTed back to this URL and processed by
        the plugin.

    .. php:method:: installAction()

    .. php:method:: activateAction()

        Action to activate a plugin

    .. php:method:: deactivateAction()

        Action to deactivate a plugin

    .. php:method:: upgradeAction()

    .. php:method:: browseAction()

        Action to browse plugins

    .. php:method:: uninstallAction()

        Action to uninstall a plugin

    .. php:method:: deleteAction()

    .. php:method:: addAction()

    .. php:method:: _getPluginByName($create = false)

        Retrieve the Plugin record based on the name passed via the request.

        :type $create: bool
        :param $create: Whether or not the plugin object should be created if it has not already been loaded.
