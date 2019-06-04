##############
files_for_item
##############

.. versionadded:: 2.7

*****
Usage
*****

Filter the HTML for displaying all files for an item.

The :doc:`file_markup` filter is used to modify the HTML markup for
displaying a single file, but this filter can be used to modify the
markup for all the files being displayed as a whole (for example, to
add markup that comes before or after, or wraps around, all the
displayed files).

*****
Value
*****

``string`` $html
    The HTML for displaying the files
    
*********
Arguments
*********

:php:class:`Item` item
    The item object
    
``array`` options
    Options to pass to the callback
    
``string`` wrapperAttributes
    Attributes to apply to the wrapping ``<div>`` element

********
See Also
********

:php:func:`files_for_item`
