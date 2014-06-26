---------------------------------
Omeka_Application_Resource_Logger
---------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Logger

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    If logging has been enabled in the config file, then set up Zend's logging
    mechanism.

    .. php:method:: init()

        :returns: Zend_Log

    .. php:method:: _addMailWriter(Zend_Log $log, $toEmail, $filter = null)

        Set up debugging emails.

        :type $log: Zend_Log
        :param $log:
        :type $toEmail: string
        :param $toEmail: Email address of debug message recipient.
        :param $filter:
