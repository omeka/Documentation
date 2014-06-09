-----------------------------
Omeka_File_Derivative_Creator
-----------------------------

.. php:class:: Omeka_File_Derivative_Creator

    Package: :doc:`File\\Derivative </Reference/packages/File/Derivative/index>`

    Create derivative images for a file in Omeka.

    .. php:attr:: _strategy
    


    .. php:attr:: _derivatives
    


    .. php:attr:: _typeBlacklist
    


    .. php:attr:: _typeWhitelist
    


    .. php:method:: create(string $sourcePath, string $derivFilename, string $mimeType)
    
        Create all the derivatives requested with addDerivative().
        
        :param string $sourcePath: 
        :param string $derivFilename: 
        :param string $mimeType: 
        :returns: boolean

    .. php:method:: addDerivative(string $storageType, integer $size)
    
        Add a derivative image to be created.
        
        :param string $storageType: 
        :param integer $size: The size constraint for the image, meaning it will have that maximum width or height, depending on whether the image is landscape or portrait.

    .. php:method:: setStrategy(Omeka_File_Derivative_StrategyInterface $strategy)
    
        Set the strategy for creating derivatives.
        
        :param Omeka_File_Derivative_StrategyInterface $strategy:

    .. php:method:: getStrategy()
    
        Get the strategy for creating derivatives.
        
        :returns: Omeka_File_Derivative_StrategyInterface

    .. php:method:: setTypeBlacklist(array|null $blacklist)
    
        Set the type blacklist.
        
        :param array|null $blacklist: An array of mime types to blacklist.

    .. php:method:: setTypeWhitelist(array|null $whitelist)
    
        Set the type whitelist.
        
        :param array|null $whitelist: An array of mime types to whitelist.

    .. php:method:: _isDerivable(string $filePath, string $mimeType)
    
        Returns whether Omeka can make derivatives of the given file.
        
        The file must be readable and pass the mime whitelist/blacklist.
        
        :param string $filePath: 
        :param string $mimeType: 
        :returns: boolean

    .. php:method:: _passesBlacklist(string $mimeType)
    
        Return whether the given type is allowed by the blacklist.
        
        If no blacklist is specified all types will pass.
        
        :param string $mimeType: 
        :returns: bool

    .. php:method:: _passesWhitelist(string $mimeType)
    
        Return whether the given type is allowed by the whitelist.
        
        If no whitelist is specified all types will pass, but anempty whitelist will reject all types.
        
        :param string $mimeType: 
        :returns: bool