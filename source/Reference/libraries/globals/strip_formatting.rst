.. _fstripformatting:

#######################################################
``strip_formatting`` — Strip HTML tags from a string.
#######################################################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/strip_formatting.rst

.. php:function:: strip_formatting($str, $allowableTags = '', $fallbackStr = '')

    Strip HTML tags from a string.
    
    This is essentially a wrapper around PHP's strip_tags() function, with the
    added benefit of returning a fallback string in case the resulting
    stripped string is empty or contains only whitespace.
    
    :type $str: string
    :param $str: The string to be stripped of HTML formatting.
    :type $allowableTags: string
    :param $allowableTags: The string of tags to allow when stripping tags.
    :type $fallbackStr: string
    :param $fallbackStr: The string to be used as a fallback.
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

