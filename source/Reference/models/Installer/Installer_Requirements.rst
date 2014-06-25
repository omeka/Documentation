----------------------
Installer_Requirements
----------------------

Package: :doc:`Install </Reference/packages/Install/index>`

.. php:class:: Installer_Requirements

    .. php:method:: check()

    .. php:method:: getErrorMessages()

    .. php:method:: getWarningMessages()

    .. php:method:: hasError()

    .. php:method:: hasWarning()

    .. php:method:: setDbAdapter(Zend_Db_Adapter_Abstract $db)

        :type $db: Zend_Db_Adapter_Abstract
        :param $db:

    .. php:method:: setStorage(Omeka_Storage $storage)

        :type $storage: Omeka_Storage
        :param $storage:

    .. php:method:: _checkPhpVersionIsValid()

    .. php:method:: _checkMysqliIsAvailable()

    .. php:method:: _checkMysqlVersionIsValid()

    .. php:method:: _checkHtaccessFilesExist()

    .. php:method:: _checkRegisterGlobalsIsOff()

    .. php:method:: _checkExifModuleIsLoaded()

    .. php:method:: _checkFileStorageSetup()

    .. php:method:: _checkFileinfoIsLoaded()
