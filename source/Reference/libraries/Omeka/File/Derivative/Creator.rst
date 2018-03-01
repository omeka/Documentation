-----------------------------
Omeka_File_Derivative_Creator
-----------------------------

Package: :doc:`File\\Derivative </Reference/packages/File/Derivative/index>`

.. php:class:: Omeka_File_Derivative_Creator

    Create derivative images for a file in Omeka.

    .. php:method:: create($sourcePath, $derivFilename, $mimeType)

        Create all the derivatives requested with addDerivative().

        :type $sourcePath: string
        :param $sourcePath:
        :type $derivFilename: string
        :param $derivFilename:
        :type $mimeType: string
        :param $mimeType:
        :returns: bool

    .. php:method:: addDerivative($storageType, $size)

        Add a derivative image to be created.

        :type $storageType: string
        :param $storageType:
        :type $size: int
        :param $size: The size constraint for the image, meaning it will have that maximum width or height, depending on whether the image is landscape or portrait.

    .. php:method:: setStrategy(Omeka_File_Derivative_StrategyInterface $strategy)

        Set the strategy for creating derivatives.

        :type $strategy: Omeka_File_Derivative_StrategyInterface
        :param $strategy:

    .. php:method:: getStrategy()

        Get the strategy for creating derivatives.

        :returns: Omeka_File_Derivative_StrategyInterface

    .. php:method:: setTypeBlacklist($blacklist)

        Set the type blacklist.

        :type $blacklist: array|null
        :param $blacklist: An array of mime types to blacklist.

    .. php:method:: setTypeWhitelist($whitelist)

        Set the type whitelist.

        :type $whitelist: array|null
        :param $whitelist: An array of mime types to whitelist.

    .. php:method:: _isDerivable($filePath, $mimeType)

        Returns whether Omeka can make derivatives of the given file.

        The file must be readable and pass the mime whitelist/blacklist.

        :type $filePath: string
        :param $filePath:
        :type $mimeType: string
        :param $mimeType:
        :returns: bool

    .. php:method:: _passesBlacklist($mimeType)

        Return whether the given type is allowed by the blacklist.

        If no blacklist is specified all types will pass.

        :type $mimeType: string
        :param $mimeType:
        :returns: bool

    .. php:method:: _passesWhitelist($mimeType)

        Return whether the given type is allowed by the whitelist.

        If no whitelist is specified all types will pass, but an empty whitelist
        will reject all types.

        :type $mimeType: string
        :param $mimeType:
        :returns: bool
