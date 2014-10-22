Controls the display of an icon to represent a file.

Valid keys for the ``$options`` array are:


* ``linkToFile``: Whether icon includes a link to the file. Takes a boolean value and default is "true".

* ``linkAttributes``: Array of additional attributes for the image link. Default attributes are ``array('class'=>'download-file', 'href'=>$file->getWebPath($derivative))``.

* ``imgAttributes``: Array of selector names and values for the image element. Default is none.

* ``icons``: Array to change default image icon. Takes the mimetype and image names in ``application/views/scripts/images``.
