----------------------
Omeka_Test_AppTestCase
----------------------

.. php:class:: Omeka_Test_AppTestCase

    Abstract test case class that bootstraps the entire application.

    .. php:attr:: _isAdminTest
    
        Flag that determines whether the test should run against admin or public.  
        Defaults to true (for admin).

    .. php:attr:: _dbChanged
    
        Optimize tests by indicating whether the database was modified during 
        the test run.  If not, the next test run can skip the Installer.

    .. php:method:: setUp()
    
        Bootstrap the application on each test run.
        
        :returns: void

    .. php:method:: __get(string $property)
    
        Proxy gets to properties to allow access to bootstrap container
        properties.
        
        :param string $property: 
        :returns: mixed

    .. php:method:: appBootstrap()
    
        Bootstrap the application.
        
        :returns: void

    .. php:method:: setUpBootstrap(Zend_Application_Bootstrap $bootstrap)
    
        Subclasses can override this to perform specialized setup on the Omeka
        application.
        
        :param Zend_Application_Bootstrap $bootstrap: 
        :returns: void

    .. php:method:: tearDown()
    
        Reset objects that carry global state between test runs.
        
        :returns: void

    .. php:method:: dispatch(string $url, boolean $throwExceptions = 1)
    
        :param string $url: 
        :param boolean $throwExceptions: 
        :returns: void

    .. php:method:: dbChanged($flag)
    
        :param unknown $flag:

    .. php:method:: _authenticateUser(User $user)
    
        Trick the environment into thinking that a user has been authenticated.
        
        :param User $user: 
        :returns: void

    .. php:method:: _getDefaultUser()
    
        Get the user that is installed by default.
        
        :returns: User

    .. php:method:: _setUpThemeBootstrap($themeType)
    
        Set up the bootstrap differently depending on whether the test is meant
        for the public or admin themes.
        
        :param unknown $themeType:

