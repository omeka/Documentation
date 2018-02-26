----------
Omeka_View
----------

Package: :doc:`View </Reference/packages/View/index>`

.. php:class:: Omeka_View

extends :php:class:`Zend_View_Abstract`

    Customized subclass of Zend Framework's View class.

    This adds the correct script paths for themes and plugins so that controllers can render the appropriate scripts.

    This will also inject directly into the view scripts all variables that have been assigned to the view, so that theme writers can access them as $item instead of $this->item, for example.

    .. php:attr:: _asset_paths

        protected array

        Maintains a key => value pairing corresponding to hard path => web path
        for possible assets for Omeka views.

    .. php:method:: __construct($config = array())

        :type $config: array
        :param $config: View configuration.

    .. php:method:: getAssetPaths()

        Get the currently-configured asset paths.

        :returns: array

    .. php:method:: addAssetPath($physical, $web)

        Add an asset path to the view.

        :type $physical: string
        :param $physical: Local filesystem path.
        :type $web: string
        :param $web: URL path.

    .. php:method:: setAssetPath($physical, $web)

        Remove the existing asset paths and set a single new one.

        :type $physical: string
        :param $physical: Local filesystem path.
        :type $web: string
        :param $web: URL path.

    .. php:method:: _run()

        Allow for variables set to the view object
        to be referenced in the view script by their actual name.

        Also allows access to theme helpers.

        For example, in a controller you might do something like:
        $view->assign('themes', $themes);
        Normally in the view you would then reference $themes through:
        $this->themes;

        Now you can reference it simply by using:
        $themes;

    .. php:method:: _loadCustomThemeScripts()

        Look for a 'custom.php' script in all script paths and include the file if
        it exists.

    .. php:method:: addScriptPath($path)

        Add a script path to the view.

        :type $path: string
        :param $path: Local filesystem path.
