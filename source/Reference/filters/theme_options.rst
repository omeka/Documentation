#############
theme_options
#############

*****
Usage
*****

Filters the theme configuration options before they are returned by a call to :php:func:`get_theme_option`.

Plugins can use this filter to modify settings for particular themes, or store and use alternative settings.

The options will be provided as a serialized string, so in order to modify the options, a plugin must unserialize() the array, make whatever changes are desired, then serialize() again before returning. 

*****
Value
*****

``string`` $themeOptions

    The set of all theme configuration options for a theme. This is a serialized array. 

*********
Arguments
*********

``string`` theme_name

    The name of the theme

********
Examples
********


