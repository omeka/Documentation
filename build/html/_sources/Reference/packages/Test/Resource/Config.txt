--------------------------
Omeka_Test_Resource_Config
--------------------------

.. php:class:: Omeka_Test_Resource_Config

    Package: :doc:`Test\\Resource </Reference/packages/Test/Resource/index>`

    Load the default config for the application, but *also* load the test config
    into Zend_Registry.

    .. php:attr:: _coreResource
    


    .. php:method:: __construct(array $options)
    
        :param array $options: Options for resource.

    .. php:method:: init()
    
        Load both config files.
        
        :returns: Zend_Config