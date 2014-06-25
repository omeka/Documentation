---------------------
Omeka_Filter_Filename
---------------------

Package: :doc:`Filter </Reference/packages/Filter/index>`

.. php:class:: Omeka_Filter_Filename

implements :php:interface:`Zend_Filter_Interface`

    Rename a file to make it suitable for inclusion in the Omeka repository.

    .. php:method:: filter($value)

        Grab the original path to the file, rename it according to our
        convention, and return the new path to the file.

        :type $value: string
        :param $value: Path to the file.
        :returns: string Path to the (renamed) file.

    .. php:method:: renameFile($name)

        Creates a new, random filename for storage in Omeka.

        :type $name: string
        :param $name:
        :returns: string
