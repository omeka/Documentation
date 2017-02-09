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

    .. php:method:: _getOffsetX($width, $size)

        Get the required offset on the X axis.

        This respects the 'gravity' setting.

        :type $width: int
        :param $width: Original image width
        :type $size: int
        :param $size: Side size of the square region being selected
        :returns: int

    .. php:method:: _getOffsetY($height, $size)

        Get the required offset on the Y axis.

        This respects the 'gravity' setting.

        :type $height: int
        :param $height: Original image height
        :type $size: int
        :param $size: Side size of square region being selected
        :returns: int
