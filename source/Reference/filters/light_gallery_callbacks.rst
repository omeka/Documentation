.. _lightgallerycallbacks:

#######################
light_gallery_callbacks
#######################

.. versionadded:: 3.2

*****
Usage
*****

Filters the callbacks used by :php:func:`lightgallery`. Adding to or modifying
these callbacks can be used to add support for more filetypes in the
lightGallery viewer, or change how supported types are displayed.

The callbacks provided to this filter each take one argument, the
:php:class:`File` object for a file to display in the gallery viewer, and
each return an array of HTML attributes to use in the lightGallery output for
that file. See `the Attributes page in the lightGallery documentation <https://www.lightgalleryjs.com/docs/attributes/>`__
for a list of possible attributes and their usage.

*****
Value
*****

``array`` $callbacks
    Array of callbacks for the gallery viewer. The keys are each
    mimetypes that should be supported by the gallery, and the values are
    PHP callables.

*********
Arguments
*********

This filter takes no additional arguments.

********
Examples
********

Add support for a filetype that needs to use a viewer with an iframe:

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = ['light_gallery_callbacks'];
    
        public filterLightGalleryCallbacks($callbacks, $args)
        {
            $callbacks['application/example-mime-type'] = 'MyPlugin::lightgallery';
            return $options;
        }

        public static function lightgallery($file)
        {
            $viewer = web_path_to('example/viewer.html');
            return [
                'data-iframe' => 'true',
                'data-iframe-title' => $file->getAltText(),
                'data-src' => $viewer . '?' . http_build_query(['file' => $file->getWebPath()]),
            ];
        }
    }
