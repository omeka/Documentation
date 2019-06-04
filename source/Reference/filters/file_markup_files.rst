#################
file_markup_files
#################

.. versionadded:: 2.7

*****
Usage
*****

Filter the set of files to be displayed by :php:func:`file_markup`

Omeka uses functions like :php:func:`files_for_item` to render all
the files attached to an item; this filter allows a developer
to alter that list, for example to exclude some files from being
displayed.

*****
Value
*****

``array`` $files
    Array of :php:class:`File` objects to be displayed
    
*********
Arguments
*********

``array`` options
    Options passed to ``file_markup``
