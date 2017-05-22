.. _file-markup-options:

The second argument, ``$props``, is an array of options to customize the display of files. Which options are valid depend on the particular file type and on whether a plugin has added a new method for displaying that file, but
there are some fairly standard available options.

Options for many possible file types can be specified all together. Each
file will only use the options that are valid for its type, and ignore the
others.

``imageSize``
  Available for images. Default: ``square_thumbnail``
  
  A string naming the size of image to use.
  The possible sizes are ``thumbnail``, ``square_thumbnail``, and
  ``fullsize``.

``linkToFile``
  Available for images and unknown-type files. Default: ``true``
  
  Whether the display should be wrapped in a direct link directly the file.
  ``true`` makes a link to the original file, ``false`` makes no link, and
  a string links to the specified image size (thumbnail, square_thumbnail,
  or fullsize).

``linkToMetadata``
  Available for images and unknown-type files. Default: ``false``
  
  If ``true``, wrap the file in a link to the file's "show" metadata page.
  This option overrides ``linkToFile`` when ``true``.

``imgAttributes``
  Available for images. Default: none

  An array of attributes to set on the HTML ``<img>`` tag. Keys of the
  array are attribute names, and values of the array are attribute values.
  
``linkText``
  Available for unknown-type files. Default: ``null``
  
  The text to display for the file (inside the link if one of the linking
  options is enabled). If null or omitted, the file's Dublin Core Title
  (if available) or original filename are used as the text.

``width``, ``height``
  Available for most audio and video types. Defaults vary.

  The pixel height and width of the audio or video player.

