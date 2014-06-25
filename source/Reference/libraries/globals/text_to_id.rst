.. _ftexttoid:

###############################################################
``text_to_id`` — Convert a word or phrase to a valid HTML ID.
###############################################################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/text_to_id.rst

.. php:function:: text_to_id($text, $prepend = null, $delimiter = '-')

    Convert a word or phrase to a valid HTML ID.
    
    For example: 'Foo Bar' becomes 'foo-bar'.
    
    This function converts to lowercase, replaces whitespace with hyphens,
    removes all non-alphanumerics, removes leading or trailing delimiters,
    and optionally prepends a piece of text.
    
    :type $text: string
    :param $text: The text to convert
    :type $prepend: string
    :param $prepend: Another string to prepend to the ID
    :type $delimiter: string
    :param $delimiter: The delimiter to use (- by default)
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/text_to_id.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/text_to_id.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/text_to_id.rst

