-------------------------------------
Omeka_Application_Resource_Autoloader
-------------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Autoloader

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    An application resource for class autoloaders.

    .. php:method:: init()

        Register autoloaders.

        Set up autoloading of the following class types from the following
        directories:
        - {@link Omeka_Form}: forms/
