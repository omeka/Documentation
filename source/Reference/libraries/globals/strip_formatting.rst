################
strip_formatting
################

.. php:function:: strip_formatting(string $str, string $allowableTags = , string $fallbackStr = )

    Strip HTML formatting (i.e. tags) from the provided string.
    
    This is essentially a wrapper around PHP's strip_tags() function, with the added benefit of returning a fallback
    string in case the resulting stripped string is empty or contains only whitespace.
    
    :param string $str: The string to be stripped of HTML formatting.
    :param string $allowableTags: The string of tags to allow when stripping tags.
    :param string $fallbackStr: The string to be used as a fallback.
    :returns: The stripped string.

*****
Usage
*****



********
Examples
********



