--------------------
Omeka_Test_Bootstrap
--------------------

Package: :doc:`Test </Reference/packages/Test/index>`

.. php:class:: Omeka_Test_Bootstrap

    Abstract test case class that bootstraps the entire application.

    .. php:method:: setContainer($container)

        Set resource container

        By default, if a resource callback has a non-null return value, this value
        will be stored in a container using the resource name as the key.

        Containers must be objects, and must allow setting public properties.

        :param $container:
        :returns: Zend_Application_Bootstrap_BootstrapAbstract

    .. php:method:: getContainer()

        Retrieve resource container

        :returns: object

    .. php:method:: hasResource($name)

        Determine if a resource has been stored in the container

        During bootstrap resource initialization, you may return a value. If you
        do, it will be stored in the {@link setContainer() container}.
        You can use this method to determine if a value was stored.

        :param $name:
        :returns: bool

    .. php:method:: getResource($name)

        Retrieve a resource from the container

        During bootstrap resource initialization, you may return a value. If you
        do, it will be stored in the {@link setContainer() container}.
        You can use this method to retrieve that value.

        If no value was returned, this will return a null value.

        :param $name:
        :returns: null|mixed
