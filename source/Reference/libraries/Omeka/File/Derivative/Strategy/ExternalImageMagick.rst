--------------------------------------------------
Omeka_File_Derivative_Strategy_ExternalImageMagick
--------------------------------------------------

Package: :doc:`File\\Derivative\\Strategy </Reference/packages/File/Derivative/Strategy/index>`

.. php:class:: Omeka_File_Derivative_Strategy_ExternalImageMagick

extends :php:class:`Omeka_File_Derivative_AbstractStrategy`

    Strategy for making derivatives with ImageMagick on the command line.

    .. php:method:: createImage($sourcePath, $destPath, $type, $sizeConstraint, $mimeType)

        Generate a derivative image from an existing file stored in Omeka.

        This image will be generated based on a constraint given in pixels.  For
        example, if the constraint is 500, the resulting image file will be scaled
        so that the largest side is 500px. If the image is less than 500px on both
        sides, the image will not be resized.

        Derivative images will only be generated for files with mime types that
        pass any configured blacklist and/or whitelist and can be processed by the
        convert binary.

        :param $sourcePath:
        :param $destPath:
        :param $type:
        :param $sizeConstraint:
        :param $mimeType:

    .. php:method:: _getConvertPath()

        Get the full path to the ImageMagick 'convert' command.

        :returns: string

    .. php:method:: _getConvertArgs($type, $constraint)

        Get the ImageMagick command line for resizing to the given constraints.

        :type $type: string
        :param $type: Type of derivative being made.
        :type $constraint: int
        :param $constraint: Maximum side length in pixels.
        :returns: string

    .. php:method:: isValidImageMagickPath($dirToIm)

        Determine whether or not the path given to ImageMagick is valid.
        The convert binary must be within the directory and executable.

        :param $dirToIm:
        :returns: bool

    .. php:method:: getDefaultImageMagickDir()

        Retrieve the path to the directory containing ImageMagick's convert
        utility.

        Uses the 'which' command-line utility to detect the path to 'convert'.
        Note that this will only work if the convert utility is in PHP's PATH and
        thus can be located by 'which'.

        :returns: string The path to the directory if it can be found.  Otherwise returns an empty string.

    .. php:method:: executeCommand($cmd, $status, $output, $errors)

        :param $cmd:
        :param $status:
        :param $output:
        :param $errors:
