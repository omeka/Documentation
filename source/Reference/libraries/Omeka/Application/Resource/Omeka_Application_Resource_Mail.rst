-------------------------------
Omeka_Application_Resource_Mail
-------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Mail

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Set up the mail transport that Omeka uses to send mail.

    This makes use of Zend_Application_Resource_Mail for configuring the mail resource. config.ini can be set up using either the Zend Framework way or using the older Omeka configuration style (for backwards-compatibility),
    though the newer style is recommended.

    .. php:method:: __construct($options = null)

        :param $options:

    .. php:method:: init()

        :returns: Zend_Mail
