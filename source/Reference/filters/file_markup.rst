
###########
file_markup
###########

*****
Usage
*****

Filter the HTML for displaying a file

*****
Value
*****

``string`` $html
    The HTML for displaying the file
    
*********
Arguments
*********

:php:class:`File` file
    The file object
    
``function`` callback
    A callback to use to generate HTML
    
``array`` options
    Options to pass to the callback
    
``string`` wrapper_attributes
    Attributes to apply to the wrapping ``<div>`` element
    
********
See Also
********

:php:func:`file_markup`, the function
