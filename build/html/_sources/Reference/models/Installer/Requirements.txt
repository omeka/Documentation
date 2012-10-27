----------------------
Installer_Requirements
----------------------

.. php:class:: Installer_Requirements

    Package: :doc:`Install </Reference/packages/Install/index>`

    .. php:attr:: _dbAdapter
    


    .. php:attr:: _storage
    


    .. php:attr:: _errorMessages
    


    .. php:attr:: _warningMessages
    


    .. php:method:: check()

    .. php:method:: getErrorMessages()

    .. php:method:: getWarningMessages()

    .. php:method:: hasError()

    .. php:method:: hasWarning()

    .. php:method:: setDbAdapter(Zend_Db_Adapter_Abstract $db)
    
        :param Zend_Db_Adapter_Abstract $db:

    .. php:method:: setStorage(Omeka_Storage $storage)
    
        :param Omeka_Storage $storage:

    .. php:method:: _checkPhpVersionIsValid()

    .. php:method:: _checkMysqliIsAvailable()

    .. php:method:: _checkMysqlVersionIsValid()

    .. php:method:: _checkHtaccessFilesExist()

    .. php:method:: _checkRegisterGlobalsIsOff()

    .. php:method:: _checkExifModuleIsLoaded()

    .. php:method:: _checkFileStorageSetup()

    .. php:method:: _checkFileinfoIsLoaded()