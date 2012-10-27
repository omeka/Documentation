--------------
Installer_Test
--------------

.. php:class:: Installer_Test

    Package: :doc:`Install </Reference/packages/Install/index>`

    Installer for test cases that require database access.

    .. php:attr:: _testDefaults
    


    .. php:attr:: _db
    


    .. php:attr:: _form
    


    .. php:method:: _getValue($fieldName)
    
        Overridden to retrieve values only from a predefined array.
        
        :param unknown $fieldName:

    .. php:method:: install()

    .. php:method:: addItem(Omeka_Db $db)
    
        :param Omeka_Db $db:

    .. php:method:: __construct(Omeka_Db $db)
    
        Constructor.
        
        :param Omeka_Db $db:

    .. php:method:: setForm(Zend_Form $form)
    
        Set the form from which to extract data for the installer.
        
        :param Zend_Form $form:

    .. php:method:: getDb()

    .. php:method:: _createSchema()

    .. php:method:: _createUser()

    .. php:method:: _setupMigrations()

    .. php:method:: _addOptions()

    .. php:method:: isInstalled()