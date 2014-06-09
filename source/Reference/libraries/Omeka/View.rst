----------
Omeka_View
----------

.. php:class:: Omeka_View

    Package: :doc:`View </Reference/packages/View/index>`

    Customized subclass of Zend Framework's View class.
    
    This adds the correct script paths for themes and plugins so that controllers can render the appropriate scripts.
    
    This will also inject directly into the view scripts all variables that havebeen assigned to the view, so that theme writers can access them as $iteminstead of $this->item, for example.

    .. php:attr:: _asset_paths
    
        Maintains a key => value pairing corresponding to hard path => web path 
        for possible assets for Omeka views.

    .. php:attr:: _customScriptsLoaded
    
        Flag indicated whether theme custom scripts have been loaded.

    .. php:method:: __construct(array $config)
    
        :param array $config: View configuration.

    .. php:method:: getAssetPaths()
    
        Get the currently-configured asset paths.
        
        :returns: array

    .. php:method:: addAssetPath(string $physical, string $web)
    
        Add an asset path to the view.
        
        :param string $physical: Local filesystem path.
        :param string $web: URL path.
        :returns: void

    .. php:method:: setAssetPath(string $physical, string $web)
    
        Remove the existing asset paths and set a single new one.
        
        :param string $physical: Local filesystem path.
        :param string $web: URL path.
        :returns: void

    .. php:method:: _run()
    
        Allow for variables set to the view object
        to be referenced in the view script by their actual name.
        
        Also allows access to theme helpers.
        
        For example, in a controller you might do something like:$view->assign('themes', $themes);Normally in the view you would then reference $themes through:$this->themes;
        
        Now you can reference it simply by using:$themes;
        
        :returns: void

    .. php:method:: _loadCustomThemeScripts()
    
        Look for a 'custom.php' script in all script paths and include the file if it exists.
        
        :returns: void

    .. php:method:: addScriptPath(string $path)
    
        Add a script path to the view.
        
        :param string $path: Local filesystem path.