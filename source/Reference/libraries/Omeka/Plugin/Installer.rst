----------------------
Omeka_Plugin_Installer
----------------------

Package: :doc:`Plugin\\Installer </Reference/packages/Plugin/Installer/index>`

.. php:class:: Omeka_Plugin_Installer

    Changes the state of any given plugin (installed/uninstalled/activated/deactivated)

    .. php:attr:: _broker

        protected Omeka_Plugin_Broker

        Plugin broker object.

    .. php:attr:: _loader

        protected Omeka_Plugin_Loader

        Plugin loader object.

    .. php:method:: __construct(Omeka_Plugin_Broker $broker, Omeka_Plugin_Loader $loader)

        :type $broker: Omeka_Plugin_Broker
        :param $broker: Plugin broker object.
        :type $loader: Omeka_Plugin_Loader
        :param $loader: Plugin loader object.

    .. php:method:: activate(Plugin $plugin)

        Activate a plugin.

        :type $plugin: Plugin
        :param $plugin: Plugin to activate.
        :returns: void

    .. php:method:: deactivate(Plugin $plugin)

        Deactivate a plugin.

        :type $plugin: Plugin
        :param $plugin: Plugin to deactivate.
        :returns: void

    .. php:method:: upgrade(Plugin $plugin)

        Upgrade a plugin.

        This will activate the plugin, then run the 'upgrade' hook.

        :type $plugin: Plugin
        :param $plugin: Plugin to upgrade.
        :returns: void

    .. php:method:: install(Plugin $plugin)

        Install a plugin.

        This will activate the plugin, then run the 'install' hook.

        :type $plugin: Plugin
        :param $plugin: Plugin to install.
        :returns: void

    .. php:method:: uninstall(Plugin $plugin)

        Uninstall a plugin.

        This will run the 'uninstall' hook for the given plugin, and then it will
        remove the entry in the DB corresponding to the plugin.

        :type $plugin: Plugin
        :param $plugin: Plugin to uninstall.
        :returns: void
