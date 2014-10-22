Controls the display of icons to represent the files associated with an item.

Valid keys for the ``$options`` array are:


* ``linkToFile``: Whether icon includes a link to the file. Takes a boolean value and default is "true".

* ``linkAttributes``: Takes an array of additional attributes for the image link. Default attributes are ``array('class'=>'download-file', 'href'=>$file->getWebPath($derivative))``.

* ``imgAttributes``: Takes an array of selector names and values for the image element. Default is none.

* ``imageSize``: Takes a value of the image size to be displayed. Valid values are ``fullsize``, ``thumbnail``, and ``square_thumbnail``.

* ``icons``: Takes an array of the MIME type and the name of an image file in ``application/views/scripts/images`` to change default image icon.
