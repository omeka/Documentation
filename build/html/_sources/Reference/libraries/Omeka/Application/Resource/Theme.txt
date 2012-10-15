--------------------------------
Omeka_Application_Resource_Theme
--------------------------------

.. php:class:: Omeka_Application_Resource_Theme

    Package: Application\Resource

    Set up the controller plugin that determines theme view script paths.

    .. php:attr:: _basePath
    
        Theme base path.
        Set by application config.

    .. php:attr:: _webBasePath
    
        Theme base URI.
        
        Set by application config.

    .. php:method:: init()

    .. php:method:: setbasepath(string $basePath)
    
        Set the base path for themes.
        Used to allow {@link $_basePath} to be set by application config.
        
        :param string $basePath:

    .. php:method:: setwebbasepath(string $webBasePath)
    
        Set the base URI for themes.
        Used to allow {@link $_webBasePath} to be set by application config.
        
        :param string $webBasePath: