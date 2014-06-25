.. _fsnippet:

############################################################
``snippet`` — Return a substring of a given piece of text.
############################################################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/snippet.rst

.. php:function:: snippet($text, $startPos, $endPos, $append = '…')

    Return a substring of a given piece of text.
    
    Note: this will only split strings on the space character.
    this will also strip html tags from the text before getting a snippet
    
    :type $text: string
    :param $text: Text to take snippet of
    :type $startPos: int
    :param $startPos: Starting position of snippet in string
    :type $endPos: int
    :param $endPos: Maximum length of snippet
    :type $append: string
    :param $append: String to append to snippet if truncated
    :returns: string Snippet of given text

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/snippet.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/snippet.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/snippet.rst

