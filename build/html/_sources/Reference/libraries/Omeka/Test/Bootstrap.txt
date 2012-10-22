--------------------
Omeka_Test_Bootstrap
--------------------

.. php:class:: Omeka_Test_Bootstrap

    Package: :doc:`/Reference/packages/Test/index`

    Abstract test case class that bootstraps the entire application.

    .. php:attr:: _container
    


    .. php:method:: setContainer($container)
    
        Set resource container
        
        By default, if a resource callback has a non-null return value, thisvalue will be stored in a container using the
        resource name as thekey.
        
        Containers must be objects, and must allow setting public properties.
        
        :param unknown $container: 
        :returns: Zend_Application_Bootstrap_BootstrapAbstract

    .. php:method:: getContainer()
    
        Retrieve resource container
        
        :returns: object

    .. php:method:: hasResource($name)
    
        Determine if a resource has been stored in the container
        
        During bootstrap resource initialization, you may return a value. Ifyou do, it will be stored in the {@link
        setContainer() container}.You can use this method to determine if a value was stored.
        
        :param unknown $name: 
        :returns: bool

    .. php:method:: getResource($name)
    
        Retrieve a resource from the container
        
        During bootstrap resource initialization, you may return a value. Ifyou do, it will be stored in the {@link
        setContainer() container}.You can use this method to retrieve that value.
        
        If no value was returned, this will return a null value.
        
        :param unknown $name: 
        :returns: null|mixed