-------------------------------------
Omeka_Application_Resource_Autoloader
-------------------------------------

.. php:class:: Omeka_Application_Resource_Autoloader

    An application resource for class autoloaders.
    
    Autoloading is also currently handled by Zend_Loader_Autoloader's fallback loader.

    .. php:method:: init()
    
        Register autoloaders.
        
        Set up autoloading of the following class types from the following directories:
        - {@link Omeka_Form}: forms/
        
        :returns: void

