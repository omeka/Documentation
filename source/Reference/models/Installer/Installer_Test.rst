--------------
Installer_Test
--------------

Package: :doc:`Install </Reference/packages/Install/index>`

.. php:class:: Installer_Test

extends :php:class:`Installer_Default`

implements :php:interface:`Installer_InstallerInterface`

    Installer for test cases that require database access.

    .. php:method:: _getValue($fieldName)

        Overridden to retrieve values only from a predefined array.

        :param $fieldName:

    .. php:method:: install()

    .. php:method:: addItem(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: __construct(Omeka_Db $db)

        Constructor.

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: setForm(Zend_Form $form)

        Set the form from which to extract data for the installer.

        :type $form: Zend_Form
        :param $form:

    .. php:method:: getDb()

    .. php:method:: _createSchema()

    .. php:method:: _createUser()

    .. php:method:: _setupMigrations()

    .. php:method:: _addOptions()

    .. php:method:: isInstalled()
