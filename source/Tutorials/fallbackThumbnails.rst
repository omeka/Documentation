############################
Changing Fallback Thumbnails
############################

Omeka displays thumbnails for files in many places. However, useful thumbnails
can't be generated for all types of files, and for some files that could have
a thumbnail, the server simply doesn't have the libraries it needs to read
that type of file and create the thumbnail.

In these situations, there is no thumbnail generated, so Omeka will use a
fallback thumbnail instead. All Omeka 2 versions have ``images/fallback-file.png``,
a simple image of a blank page used to represent files generically. Omeka 2.2
adds more specific fallbacks for audio, video and image files.

*******************************
Overriding thumbnails in themes
*******************************

The fallback thumbnails are simply theme assets, so they can be overridden by
a theme just including its own image in the same location. The default 
fallbacks are located in ``application/views/scripts/images`` and are PNG images
with names starting with ``fallback-``. ``fallback-file.png`` is present in all
Omeka versions, and Omeka 2.2 adds ``fallback-audio.png``, ``fallback-video.png``
and ``fallback-image.png``.

In a theme, you can just put your own versions of those files in the theme's
``images`` folder. The default images are 200x200 pixel square PNGs.

******************************
Adding new fallback thumbnails
******************************

In addition to just overriding the existing thumbnails, you can also add new
fallbacks with a plugin.

The function :php:func:`add_file_fallback_image` is used to add a new fallback
image for a given MIME type or type family. The first argument is the MIME type
the fallback will apply to, and the second is the name of the image to use. The image
name is internally passed to :php:func:`img`. The plugin should place the actual
fallback image in its ``views/shared/images`` folder.

The fallback will only be used for files lacking thumbnails that match the MIME type
(or family) you pass. The "family" is the part of the MIME type before the slash, "image"
for "image/jpeg" for example.

The call to :php:func:`!add_file_fallback_image` should be made in the plugin's
:doc:`/Reference/hooks/initialize` hook.
