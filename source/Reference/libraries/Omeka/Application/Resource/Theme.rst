--------------------------------
Omeka_Application_Resource_Theme
--------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Theme

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Set up the controller plugin that determines theme view script paths.

    .. php:attr:: _basePath

        protected string

        Theme base path.
        Set by application config.

    .. php:attr:: _webBasePath

        protected string

        Theme base URI.

        Set by application config.

    .. php:method:: init()

    .. php:method:: setbasepath($basePath)

        Set the base path for themes.
        Used to allow {@link $_basePath} to be set by application config.

        :type $basePath: string
        :param $basePath:

    .. php:method:: setwebbasepath($webBasePath)

        Set the base URI for themes.
        Used to allow {@link $_webBasePath} to be set by application config.

        :type $webBasePath: string
        :param $webBasePath:
