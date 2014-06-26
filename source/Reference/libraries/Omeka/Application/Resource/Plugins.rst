----------------------------------
Omeka_Application_Resource_Plugins
----------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Plugins

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Fire the 'initialize' hook for all installed plugins.

    Note that this hook fires before the front controller has been initialized or dispatched.

    .. php:method:: init()
