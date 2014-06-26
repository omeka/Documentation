-----------------
Installer_Default
-----------------

Package: :doc:`Install </Reference/packages/Install/index>`

.. php:class:: Installer_Default

implements :php:interface:`Installer_InstallerInterface`

    The default installer, which extracts values from the installer form to
    create the default Omeka installation.

    .. php:method:: __construct(Omeka_Db $db)

        Constructor.

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: setForm(Zend_Form $form)

        Set the form from which to extract data for the installer.

        :type $form: Zend_Form
        :param $form:

    .. php:method:: getDb()

    .. php:method:: install()

    .. php:method:: _getValue($fieldName)

        :param $fieldName:

    .. php:method:: _createSchema()

    .. php:method:: _createUser()

    .. php:method:: _setupMigrations()

    .. php:method:: _addOptions()

    .. php:method:: isInstalled()
