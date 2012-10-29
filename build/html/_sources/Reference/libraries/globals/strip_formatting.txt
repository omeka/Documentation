################
strip_formatting
################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/strip_formatting.rst

.. php:function:: strip_formatting(string $str, string $allowableTags = , string $fallbackStr = )

    Strip HTML formatting (i.e. tags) from the provided string.
    
    This is essentially a wrapper around PHP's strip_tags() function, with theadded benefit of returning a fallback string in case the resulting strippedstring is empty or contains only whitespace.
    
    :param string $str: The string to be stripped of HTML formatting.
    :param string $allowableTags: The string of tags to allow when stripping tags.
    :param string $fallbackStr: The string to be used as a fallback.
    :returns: The stripped string.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/strip_formatting.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/strip_formatting.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/strip_formatting.rst

