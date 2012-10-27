##################
text_to_paragraphs
##################

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/text_to_paragraphs.rst

.. php:function:: text_to_paragraphs(string $str)

    Replace new lines in a block of text with paragraph tags.
    
    Looks for 2 consecutive line breaks resembling a paragraph break and wrapseach of the paragraphs with a <p> tag.  If
    no paragraphs are found, then theoriginal text will be wrapped with line breaks.
    
    :param string $str: 
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/text_to_paragraphs.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/text_to_paragraphs.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/text_to_paragraphs.rst

