############
storage_path
############

*****
Usage
*****

Changes the path to where a file is stored. This can be a simpler solution than writing your own storage adapter class.

*****
Value
*****

``string`` $path

    The path to the file, e.g. ``files/image1.jpg``

*********
Arguments
*********

``string`` type

    The type of path, e.g. ``files``
    
``string`` filename

    The filename, e.g. ``image1.jpg``    

********
Examples
********

Store files in different directories by extension.

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('storage_path');
        
        public filterStoragePath($path, $args)
        {
            $explodedFileName = explode('.', $args['filename']);
            $extension = $explodedFileName[count($explodedFileName)-1];
            return 'files/' . $extension . '/' . $args['filename'];
        }    
    }


********
See Also
********

:php:class:`Omeka_Storage`