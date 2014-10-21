Valid keys for the ``$options`` array are:

* ``showFilename``: Whether to display the filename. Takes a boolean value and the default is "true".

* ``linkToFile``: Whether icon includes a link to the file. Takes a boolean value and default is "true".

* ``linkAttributes``: Array of additional attributes for the item link. Default attributes are ``array('class'=>'download-file', 'href'=>$file->getWebPath($derivative))``.

* ``filenameAttributes``: Array of selector names and values for the filename element. Default is none.

* ``imgAttributes``: Array of selector names and values for the image element. Default is none.

* ``icons``: Array to change default image icon. Takes the mimetype and image names in ``application/views/scripts/images``.