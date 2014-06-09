----------------------------
Omeka_View_Helper_FileMarkup
----------------------------

.. php:class:: Omeka_View_Helper_FileMarkup

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    View Helper for displaying files through Omeka.
    
    This will determine how to display any given file based on the MIME type(Internet media type) of that file. Individual rendering agents are definedby callbacks that are either contained within this class or defined byplugins. Callbacks defined by plugins will override native class methods ifdefined for existing MIME types. In order to define a rendering callback thatshould be in the core of Omeka, define a method in this class and then makesure that it responds to all the correct MIME types by modifying otherproperties in this class.

    .. php:const:: GENERIC_FALLBACK_IMAGE
    
    
    
        Fallback image used when no other fallbacks are appropriate.

    .. php:attr:: _callbacks
    
        Array of MIME types and the callbacks that can process it.
        
        Example:array('video/avi'=>'wmv');

    .. php:attr:: _fileExtensionCallbacks
    
        Array of file extensions and the callbacks that can process them.
        
        Taken from http://svn.apache.org/repos/asf/httpd/httpd/trunk/docs/conf/mime.types

    .. php:attr:: _callbackOptions
    
        The array consists of the default options which are passed to the 
        callback.

    .. php:attr:: _fallbackImages
    
        Images to show when a file has no derivative.

    .. php:method:: addMimeTypes(array|string $fileIdentifiers, $callback, array $defaultOptions)
    
        Add MIME types and/or file extensions and associated callbacks to the 
        list.
        
        This allows plugins to override/define ways of displaying specific files.The most obvious example of where this would come in handy is to defineways of displaying uncommon files, such as QTVR, or novel ways ofdisplaying more common files, such as using iPaper to display PDFs.
        
        :param array|string $fileIdentifiers: Set of MIME types (Internet media types) and/or file extensions that this specific callback will respond to. Accepts the following:         
        
            .. raw:: html
        
               <ul>
                     <li>A string containing one MIME type: 
                     <code>'application/msword'</code></li>
                     <li>A simple array containing MIME types: 
                     <code>array('application/msword', 'application/doc')</code></li>
                     <li>A keyed array containing MIME types: 
                     <code>array('mimeTypes' => array('application/msword', 'application/doc'))</code></li>
                     <li>A keyed array containing file extensions: 
                     <code>array('fileExtensions' => array('doc', 'docx''DOC', 'DOCX'))</code></li>
                     <li>A keyed array containing MIME types and file extensions: <code>
                     array(
                         'mimeTypes' => array(
                             'application/msword', 
                             'application/doc', 
                             'application/vnd.openxmlformats-officedocument.wordprocessingml.document', 
                         ), 
                         'fileExtensions' => array('doc', 'docx', 'DOC', 'DOCX'), 
                     )
                     </code></li>
                 </ul>
         Note that file extensions are case sensitive.
        :param unknown $callback: 
        :param array $defaultOptions: 
        :returns: void

    .. php:method:: addFallbackImage(string $mimeType, string $image)
    
        Add a fallback image for the given mime type or type family.
        
        :param string $mimeType: The mime type this fallback is for, or the mime "prefix" it is for (video, audio, etc.)
        :param string $image: The name of the image to use, as would be passed to img()

    .. php:method:: defaultDisplay(File $file, array $options)
    
        Default display for MIME types that do not have a valid rendering 
        callback.
        
        This wraps the original filename in a link to download that file, with aclass of "download-file".  Any behavior more complex than that should beprocessed with a valid callback.
        
        :param File $file: 
        :param array $options: 
        :returns: string HTML

    .. php:method:: _linkToFile(File $file, array $options, string $html)
    
        Add a link for the file based on the given set of options.
        
        If the 'linkToMetadata' option is true, then link to the filemetadata page (files/show).  If 'linkToFile' is true,link to the original file, and if 'linkToFile' is a string, tryto link to that specific derivative. Otherwise just return the$html without wrapping in a link.
        
        The attributes for the link will be based off the 'linkAttributes' 
        option, which should be an array.
        
        If $html is null, it defaults to original filename of the file.
        
        :param File $file: 
        :param array $options: 
        :param string $html: 
        :returns: string

    .. php:method:: wmv(File $file, array $options)
    
        Retrieve valid XHTML for displaying a wmv video file or equivalent.  
        Currently this loads the video inside of an <object> tag, but that 
        provides less flexibility than a flash wrapper, which seems to be a 
        standard Web2.0 practice for video sharing.  This limitation can be
        overcome by a plugin that used a flash wrapper for displaying video.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: wma(File $file, array $options)
    
        Retrieve valid XHTML for displaying a wma audio file or equivalent.  
        Currently this loads the video inside of an <object> tag, but that
        provides less flexibility than a flash wrapper, which seems to be a 
        standard Web2.0 practice for video sharing.  This limitation can be
        overcome by a plugin that used a flash wrapper for displaying video.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: mov(File $file, array $options)
    
        Retrieve valid XHTML for displaying Quicktime video files
        
        :param File $file: 
        :param array $options: The set of default options for this includes: width, height, autoplay, controller, loop
        :returns: string

    .. php:method:: _audio(File $file, array $options, string $type)
    
        Default display of audio files via <object> tags.
        
        :param File $file: 
        :param array $options: The set of default options for this includes: width, height, autoplay, controller, loop
        :param string $type: The Internet media type of the file
        :returns: string

    .. php:method:: ogg(File $file, array $options)
    
        Display OGG audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: mp3(File $file, array $options)
    
        Display MP3/MPEG audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: aac(File $file, array $options)
    
        Display AAC audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: aiff(File $file, array $options)
    
        Display AIFF audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: midi(File $file, array $options)
    
        Display MIDI audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: mp4(File $file, array $options)
    
        Display MP4 audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: wav(File $file, array $options)
    
        Display WAV audio files.
        
        :param File $file: 
        :param array $options: 
        :returns: string

    .. php:method:: icon($file, array $options)
    
        Default display of an icon to represent a file.
        
        Example usage:
        
        echo files_for_item(array('showFilename'=>false,'linkToFile'=>false,'linkAttributes'=>array('rel'=>'lightbox'),'filenameAttributes'=>array('class'=>'error'),'imgAttributes'=>array('id'=>'foobar'),'icons' => array('audio/mpeg'=>img('audio.gif'))));
        
        :param unknown $file: 
        :param array $options: Available options include: 'showFilename' => boolean, 'linkToFile' => boolean, 'linkAttributes' => array, 'filenameAttributes' => array (for the filename div), 'imgAttributes' => array, 'icons' => array.
        :returns: string

    .. php:method:: derivativeImage(File $file, $options)
    
        Returns valid XHTML markup for displaying an image that has been stored 
        in Omeka.
        
        :param File $file: Options for customizing the display of images. Current options include: 'imageSize'
        :param unknown $options: 
        :returns: string HTML for display

    .. php:method:: getCallback($file, $options)
    
        :param unknown $file: 
        :param unknown $options:

    .. php:method:: getDefaultOptions(mixed $callback)
    
        :param mixed $callback: 
        :returns: array

    .. php:method:: getHtml(File $file, callback $renderer, array $options)
    
        Retrieve the HTML for a given file from the callback.
        
        :param File $file: 
        :param callback $renderer: Any valid callback that will display the HTML.
        :param array $options: Set of options passed to the rendering callback.
        :returns: string HTML for displaying the file.

    .. php:method:: fileMarkup(File $file, array $props, array $wrapperAttributes)
    
        Bootstrap for the helper class.  This will retrieve the HTML for
        displaying the file and by default wrap it in a <div class="item-file">.
        
        :param File $file: 
        :param array $props: Set of options passed by a theme writer to the customize the display of any given callback.
        :param array $wrapperAttributes: 
        :returns: string HTML

    .. php:method:: image_tag(File|Item $record, array $props, string $format)
    
        Return a valid img tag for an image.
        
        :param File|Item $record: 
        :param array $props: 
        :param string $format: 
        :returns: string

    .. php:method:: _getFallbackImage(File $file)
    
        Get the name of a fallback image to use for this file.
        
        The fallback used depends on the file's mime type.
        
        :param File $file: The file to get a fallback for.
        :returns: string Name of the image to use.

    .. php:method:: _getCallbackKey(callback $callback)
    
        Get a string key to represent a given callback.
        
        This key can be used to store and retrieve data about thecallback, like default options.
        
        :param callback $callback: 
        :returns: string