--------------------------------------
Omeka_File_Derivative_Strategy_Imagick
--------------------------------------

Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

.. php:class:: Omeka_File_Derivative_Strategy_Imagick

extends :php:class:`Omeka_File_Derivative_AbstractStrategy`

    Strategy for making derivatives with the Imagick PHP extension.

    The strategy requires ext/imagick.

    .. php:method:: __construct()

        Check for the imagick extension at creation.

    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)

        Generate a derivative image with Imagick.

        :param $sourcePath:
        :param $destPath:
        :param $type:
        :param $sizeConstraint:
        :param $mimeType:

    .. php:method:: _getCropOffsetX($resizedX, $sizeConstraint)

        Get the required crop offset on the X axis.

        This respects the 'gravity' setting.

        :type $resizedX: int
        :param $resizedX: Pre-crop image width
        :type $sizeConstraint: int
        :param $sizeConstraint:
        :returns: int

    .. php:method:: _getCropOffsetY($resizedY, $sizeConstraint)

        Get the required crop offset on the Y axis.

        This respects the 'gravity' setting.

        :type $resizedY: int
        :param $resizedY: Pre-crop image height
        :type $sizeConstraint: int
        :param $sizeConstraint:
        :returns: int

    .. php:method:: _autoOrient($imagick)

        :param $imagick:
