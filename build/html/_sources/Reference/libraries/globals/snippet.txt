#######
snippet
#######

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/snippet.rst

.. php:function:: snippet(string $text, int $startPos, int $endPos, string $append = …)

    Return a substring of a given piece of text.
    
    Note: this will only split strings on the space character.this will also strip html tags from the text before getting a snippet
    
    :param string $text: Text to take snippet of
    :param int $startPos: Starting position of snippet in string
    :param int $endPos: Maximum length of snippet
    :param string $append: String to append to snippet if truncated
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

