---------------------------------------
Omeka_File_Derivative_StrategyInterface
---------------------------------------

Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

.. php:interface:: Omeka_File_Derivative_StrategyInterface

    Interface for pluggable file derivative creation strategies.

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

    .. php:method:: setOptions($options)

        Set options for the derivative strategy.

        :type $options: array
        :param $options:

    .. php:method:: getOptions()

        Get the options for the strategy.

        :returns: array
