``file_markup`` can be passed just a file or array of files alone to
produce the default display::

    // Display one specific File
    echo file_markup($file);
    
    // Display all the given Files (here, the files for an Item)
    echo file_markup($item->Files);

One of the simplest uses of ``file_markup``'s display options is to display
a fullsize image instead of a small square thumbnail::

    echo file_markup($file, array('imageSize' => 'fullsize'));
