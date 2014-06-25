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

        :returns: void

    .. php:method:: installAction()

    .. php:method:: activateAction()

        Action to activate a plugin

        :returns: void

    .. php:method:: deactivateAction()

        Action to deactivate a plugin

        :returns: void

    .. php:method:: upgradeAction()

    .. php:method:: browseAction()

        Action to browse plugins

        :returns: void

    .. php:method:: uninstallAction()

        Action to uninstall a plugin

        :returns: void

    .. php:method:: deleteAction()

    .. php:method:: addAction()

    .. php:method:: _getPluginByName($create = false)

        Retrieve the Plugin record based on the name passed via the request.

        :type $create: boolean
        :param $create: Whether or not the plugin object should be created if it has not already been loaded.
