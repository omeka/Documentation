---------------------
Omeka_Filter_Filename
---------------------

.. php:class:: Omeka_Filter_Filename

    Package: :doc:`/Reference/packages/Filter/index`

    Rename a file to make it suitable for inclusion in the Omeka repository.

    .. php:method:: filter(string $value)
    
        Grab the original path to the file, rename it according to our 
        convention, and return the new path to the file.
        
        :param string $value: Path to the file.
        :returns: string Path to the (renamed) file.

    .. php:method:: renameFile(string $name)
    
        Creates a new, random filename for storage in Omeka.
        
        :param string $name: 
        :returns: string