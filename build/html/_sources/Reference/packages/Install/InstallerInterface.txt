----------------------------
Installer_InstallerInterface
----------------------------

.. php:class:: Installer_InstallerInterface

    Package: :doc:`/Reference/packages/Install/index`

    Interface for creating different installers for Omeka.

    .. php:method:: __construct(Omeka_Db $db)
    
        :param Omeka_Db $db:

    .. php:method:: install()

    .. php:method:: isInstalled()