-----------------
Installer_Default
-----------------

.. php:class:: Installer_Default

    Package: :doc:`/Reference/packages/Install/index`

    The default installer, which extracts values from the installer form to 
    create the default Omeka installation.

    .. php:attr:: _db
    


    .. php:attr:: _form
    


    .. php:method:: __construct(Omeka_Db $db)
    
        Constructor.
        
        :param Omeka_Db $db:

    .. php:method:: setForm(Zend_Form $form)
    
        Set the form from which to extract data for the installer.
        
        :param Zend_Form $form:

    .. php:method:: getDb()

    .. php:method:: install()

    .. php:method:: _getValue($fieldName)
    
        :param unknown $fieldName:

    .. php:method:: _createSchema()

    .. php:method:: _createUser()

    .. php:method:: _setupMigrations()

    .. php:method:: _addOptions()

    .. php:method:: isInstalled()