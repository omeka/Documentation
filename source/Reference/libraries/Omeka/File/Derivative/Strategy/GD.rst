---------------------------------
Omeka_File_Derivative_Strategy_GD
---------------------------------

Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

.. php:class:: Omeka_File_Derivative_Strategy_GD

extends :php:class:`Omeka_File_Derivative_AbstractStrategy`

    Strategy for making derivatives with the GD PHP library (default since 4.3).

    .. php:method:: __construct()

        Check for the imagick extension at creation.

    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)

        Generate a derivative image with GD.

        :param $sourcePath:
        :param $destPath:
        :param $type:
        :param $sizeConstraint:
        :param $mimeType:
        :returns: boolean Returns true on success or false on failure.

    .. php:method:: _loadImageResource($source)

        GD uses multiple functions to load an image, so this one manages all.

        :type $source: string
        :param $source: Path of the managed image file
        :returns: false|GD image ressource

    .. php:method:: _makeThumbnail($source, $destination, $sizeConstraint)

        Make a thumbnail from source and save it at destination.

        :type $source: string
        :param $source: Path of the source.
        :type $destination: string
        :param $destination: Path of the destination.
        :type $sizeConstraint: integer
        :param $sizeConstraint: Maximum size in pixels.
        :returns: boolean Returns true on success or false on failure.

    .. php:method:: _makeSquareThumbnail($source, $destination, $sizeConstraint)

        Make a square thumbnail from source and save it at destination.

        :type $source: string
        :param $source: Path of the source.
        :type $destination: string
        :param $destination: Path of the destination.
        :type $sizeConstraint: integer
        :param $sizeConstraint: Maximum size in pixels.
        :returns: boolean Returns true on success or false on failure.

    .. php:method:: _getCropOffsetX($resizedX, $sizeConstraint)

        Get the required crop offset on the X axis.

        This respects the Imagick 'gravity' setting.

        :type $resizedX: int
        :param $resizedX: Pre-crop image width
        :type $sizeConstraint: int
        :param $sizeConstraint:
        :returns: int

    .. php:method:: _getCropOffsetY($resizedY, $sizeConstraint)

        Get the required crop offset on the Y axis.

        This respects the Imagick 'gravity' setting.

        :type $resizedY: int
        :param $resizedY: Pre-crop image height
        :type $sizeConstraint: int
        :param $sizeConstraint:
        :returns: int
