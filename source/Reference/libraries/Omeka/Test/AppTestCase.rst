----------------------
Omeka_Test_AppTestCase
----------------------

Package: :doc:`Test </Reference/packages/Test/index>`

.. php:class:: Omeka_Test_AppTestCase

extends :php:class:`Zend_Test_PHPUnit_ControllerTestCase`

    Abstract test case class that bootstraps the entire application.

    .. php:attr:: _isAdminTest

        protected bool

        Flag that determines whether the test should run against admin or public.

        Defaults to true (for admin).

    .. php:method:: setUp()

        Bootstrap the application on each test run.

    .. php:method:: __get($property)

        Proxy gets to properties to allow access to bootstrap container
        properties.

        :type $property: string
        :param $property:
        :returns: mixed

    .. php:method:: appBootstrap()

        Bootstrap the application.

    .. php:method:: setUpBootstrap($bootstrap)

        Subclasses can override this to perform specialized setup on the Omeka
        application.

        :type $bootstrap: Zend_Application_Bootstrap
        :param $bootstrap:

    .. php:method:: tearDown()

        Reset objects that carry global state between test runs.

    .. php:method:: dispatch($url = null, $throwExceptions = true)

        :type $url: string
        :param $url:
        :type $throwExceptions: bool
        :param $throwExceptions:

    .. php:method:: _authenticateUser(User $user)

        Trick the environment into thinking that a user has been authenticated.

        :type $user: User
        :param $user:

    .. php:method:: _getDefaultUser()

        Get the user that is installed by default.

        :returns: User

    .. php:method:: _setUpThemeBootstrap($themeType)

        Set up the bootstrap differently depending on whether the test is meant
        for the public or admin themes.

        :param $themeType:
