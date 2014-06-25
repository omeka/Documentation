--------------------------------------
Omeka_File_Derivative_AbstractStrategy
--------------------------------------

Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

.. php:class:: Omeka_File_Derivative_AbstractStrategy

implements :php:interface:`Omeka_File_Derivative_StrategyInterface`

    Abstract class for pluggable file derivative creation strategies.

    .. php:attr:: _options

        protected

    .. php:method:: setOptions($options)

        Set options for the derivative strategy.

        :type $options: array
        :param $options:

    .. php:method:: getOptions()

        Get the options for the strategy.

        :returns: array

    .. php:method:: getOption($name, $default = null)

        Get the value for the specified option.

        :type $name: string
        :param $name: Name of the option to get
        :type $default: mixed
        :param $default: Default value to return if the option is missing. Defaults to null.
        :returns: mixed

    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)

        Create an derivative of the given image.

        :type $sourcePath: string
        :param $sourcePath: Local path to the source file.
        :type $destPath: string
        :param $destPath: Local path to write the derivative to.
        :type $type: string
        :param $type: The type of derivative being created.
        :type $sizeConstraint: int
        :param $sizeConstraint: Size limitation on the derivative.
        :type $mimeType: string
        :param $mimeType: MIME type of the original file.
        :returns: bool
