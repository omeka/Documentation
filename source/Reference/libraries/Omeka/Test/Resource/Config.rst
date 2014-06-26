--------------------------
Omeka_Test_Resource_Config
--------------------------

Package: :doc:`Test\\Resource </Reference/packages/Test/Resource/index>`

.. php:class:: Omeka_Test_Resource_Config

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Load the default config for the application, but *also* load the test config
    into Zend_Registry.

    .. php:method:: __construct($options = null)

        :type $options: array
        :param $options: Options for resource.

    .. php:method:: init()

        Load both config files.

        :returns: Zend_Config
