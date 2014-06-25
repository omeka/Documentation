----------------------
Omeka_Test_AppTestCase
----------------------

Package: :doc:`Test </Reference/packages/Test/index>`

.. php:class:: Omeka_Test_AppTestCase

extends :php:class:`Zend_Test_PHPUnit_ControllerTestCase`

    Abstract test case class that bootstraps the entire application.

    .. php:attr:: _isAdminTest

        protected boolean

        Flag that determines whether the test should run against admin or public.

        Defaults to true (for admin).

    .. php:method:: setUp()

        Bootstrap the application on each test run.

        :returns: void

    .. php:method:: __get($property)

        Proxy gets to properties to allow access to bootstrap container
        properties.

        :type $property: string
        :param $property:
        :returns: mixed

    .. php:method:: appBootstrap()

        Bootstrap the application.

        :returns: void

    .. php:method:: setUpBootstrap($bootstrap)

        Subclasses can override this to perform specialized setup on the Omeka
        application.

        :type $bootstrap: Zend_Application_Bootstrap
        :param $bootstrap:
        :returns: void

    .. php:method:: tearDown()

        Reset objects that carry global state between test runs.

        :returns: void

    .. php:method:: dispatch($url = null, $throwExceptions = true)

        :type $url: string
        :param $url:
        :type $throwExceptions: boolean
        :param $throwExceptions:
        :returns: void

    .. php:method:: _authenticateUser(User $user)

        Trick the environment into thinking that a user has been authenticated.

        :type $user: User
        :param $user:
        :returns: void

    .. php:method:: _getDefaultUser()

        Get the user that is installed by default.

        :returns: User

    .. php:method:: _setUpThemeBootstrap($themeType)

        Set up the bootstrap differently depending on whether the test is meant
        for the public or admin themes.

        :param $themeType:
