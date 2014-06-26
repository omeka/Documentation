----------------------------
Omeka_View_Helper_FileMarkup
----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_FileMarkup

extends :php:class:`Zend_View_Helper_Abstract`

    View Helper for displaying files through Omeka.

    This will determine how to display any given file based on the MIME type
    (Internet media type) of that file. Individual rendering agents are defined by callbacks that are either contained within this class or defined by plugins. Callbacks defined by plugins will override native class methods if defined for existing MIME types. In order to define a rendering callback that should be in the core of Omeka, define a method in this class and then make sure that it responds to all the correct MIME types by modifying other properties in this class.

    .. php:const:: GENERIC_FALLBACK_IMAGE

        Fallback image used when no other fallbacks are appropriate.

    .. php:attr:: _callbacks

        protected array

        Array of MIME types and the callbacks that can process it.

        Example:
        array('video/avi'=>'wmv');

    .. php:attr:: _callbackOptions

        protected array

        The array consists of the default options which are passed to the
        callback.

    .. php:attr:: _fallbackImages

        protected array

        Images to show when a file has no derivative.

    .. php:method:: addMimeTypes($fileIdentifiers, $callback, $defaultOptions = array())

        Add MIME types and/or file extensions and associated callbacks to the
        list.

        This allows plugins to override/define ways of displaying specific files.
        The most obvious example of where this would come in handy is to define
        ways of displaying uncommon files, such as QTVR, or novel ways of
        displaying more common files, such as using iPaper to display PDFs.

        :type $fileIdentifiers: array|string
        :param $fileIdentifiers: Set of MIME types (Internet media types) and/or file extensions that this specific callback will respond to. Accepts the following: <ul> <li>A string containing one MIME type: <code>'application/msword'</code></li> <li>A simple array containing MIME types: <code>array('application/msword', 'application/doc')</code></li> <li>A keyed array containing MIME types: <code>array('mimeTypes' => array('application/msword', 'application/doc'))</code></li> <li>A keyed array containing file extensions: <code>array('fileExtensions' => array('doc', 'docx''DOC', 'DOCX'))</code></li> <li>A keyed array containing MIME types and file extensions: <code> array( 'mimeTypes' => array( 'application/msword', 'application/doc', 'application/vnd.openxmlformats-officedocument.wordprocessingml.document', ), 'fileExtensions' => array('doc', 'docx', 'DOC', 'DOCX'), ) </code></li> </ul> Note that file extensions are case sensitive.
        :param $callback:
        :type $defaultOptions: array
        :param $defaultOptions:
        :returns: void

    .. php:method:: addFallbackImage($mimeType, $image)

        Add a fallback image for the given mime type or type family.

        :type $mimeType: string
        :param $mimeType: The mime type this fallback is for, or the mime "prefix" it is for (video, audio, etc.)
        :type $image: string
        :param $image: The name of the image to use, as would be passed to img()

    .. php:method:: defaultDisplay($file, $options = array())

        Default display for MIME types that do not have a valid rendering
        callback.

        This wraps the original filename in a link to download that file, with a
        class of "download-file".  Any behavior more complex than that should be
        processed with a valid callback.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string HTML

    .. php:method:: _linkToFile($file, $options, $html = null)

        Add a link for the file based on the given set of options.

        If the 'linkToMetadata' option is true, then link to the file metadata
        page (files/show).  If 'linkToFile' is true,
        link to the original file, and if 'linkToFile' is a string, try to link to
        that specific derivative. Otherwise just return the
        $html without wrapping in a link.

        The attributes for the link will be based off the 'linkAttributes'
        option, which should be an array.

        If $html is null, it defaults to original filename of the file.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :type $html: string
        :param $html:
        :returns: string

    .. php:method:: wmv($file, $options = array())

        Retrieve valid XHTML for displaying a wmv video file or equivalent.
        Currently this loads the video inside of an <object> tag, but that
        provides less flexibility than a flash wrapper, which seems to be a
        standard Web2.0 practice for video sharing.  This limitation can be
        overcome by a plugin that used a flash wrapper for displaying video.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: wma($file, $options = array())

        Retrieve valid XHTML for displaying a wma audio file or equivalent.
        Currently this loads the video inside of an <object> tag, but that
        provides less flexibility than a flash wrapper, which seems to be a
        standard Web2.0 practice for video sharing.  This limitation can be
        overcome by a plugin that used a flash wrapper for displaying video.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: mov($file, $options = array())

        Retrieve valid XHTML for displaying Quicktime video files

        :type $file: File
        :param $file:
        :type $options: array
        :param $options: The set of default options for this includes: width, height, autoplay, controller, loop
        :returns: string

    .. php:method:: _audio($file, $options, $type)

        Default display of audio files via <object> tags.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options: The set of default options for this includes: width, height, autoplay, controller, loop
        :type $type: string
        :param $type: The Internet media type of the file
        :returns: string

    .. php:method:: ogg($file, $options = array())

        Display OGG audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: mp3($file, $options = array())

        Display MP3/MPEG audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: aac($file, $options = array())

        Display AAC audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: aiff($file, $options = array())

        Display AIFF audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: midi($file, $options = array())

        Display MIDI audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: mp4($file, $options = array())

        Display MP4 audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: wav($file, $options = array())

        Display WAV audio files.

        :type $file: File
        :param $file:
        :type $options: array
        :param $options:
        :returns: string

    .. php:method:: icon($file, $options = array())

        Default display of an icon to represent a file.

        Example usage:

        echo files_for_item(array(
        'showFilename'=>false,
        'linkToFile'=>false,
        'linkAttributes'=>array('rel'=>'lightbox'),
        'filenameAttributes'=>array('class'=>'error'),
        'imgAttributes'=>array('id'=>'foobar'),
        'icons' => array('audio/mpeg'=>img('audio.gif'))));

        :param $file:
        :type $options: array
        :param $options: Available options include: 'showFilename' => boolean, 'linkToFile' => boolean, 'linkAttributes' => array, 'filenameAttributes' => array (for the filename div), 'imgAttributes' => array, 'icons' => array.
        :returns: string

    .. php:method:: derivativeImage($file, $options = array())

        Returns valid XHTML markup for displaying an image that has been stored
        in Omeka.

        :type $file: File
        :param $file: Options for customizing the display of images. Current options include: 'imageSize'
        :param $options:
        :returns: string HTML for display

    .. php:method:: getCallback($file, $options)

        :param $file:
        :param $options:

    .. php:method:: getDefaultOptions($callback)

        :type $callback: mixed
        :param $callback:
        :returns: array

    .. php:method:: getHtml($file, $renderer, $options)

        Retrieve the HTML for a given file from the callback.

        :type $file: File
        :param $file:
        :type $renderer: callback
        :param $renderer: Any valid callback that will display the HTML.
        :type $options: array
        :param $options: Set of options passed to the rendering callback.
        :returns: string HTML for displaying the file.

    .. php:method:: fileMarkup($file, $props = array(), $wrapperAttributes = array())

        Bootstrap for the helper class.  This will retrieve the HTML for
        displaying the file and by default wrap it in a <div class="item-file">.

        :type $file: File
        :param $file:
        :type $props: array
        :param $props: Set of options passed by a theme writer to the customize the display of any given callback.
        :type $wrapperAttributes: array
        :param $wrapperAttributes:
        :returns: string HTML

    .. php:method:: image_tag($record, $props, $format)

        Return a valid img tag for an image.

        :type $record: File|Item
        :param $record:
        :type $props: array
        :param $props:
        :type $format: string
        :param $format:
        :returns: string

    .. php:method:: _getFallbackImage($file)

        Get the name of a fallback image to use for this file.

        The fallback used depends on the file's mime type.

        :type $file: File
        :param $file: The file to get a fallback for.
        :returns: string Name of the image to use.

    .. php:method:: _getCallbackKey($callback)

        Get a string key to represent a given callback.

        This key can be used to store and retrieve data about the callback, like
        default options.

        :type $callback: callback
        :param $callback:
        :returns: string
