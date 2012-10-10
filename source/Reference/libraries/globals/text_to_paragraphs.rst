##################
text_to_paragraphs
##################

*******
Summary
*******

.. include:: summary/text_to_paragraphs.rst

.. php:function:: text_to_paragraphs(string $str)

    Replace new lines in a block of text with paragraph tags.
    
    Looks for 2 consecutive line breaks resembling a paragraph break and wraps each of the paragraphs with a <p> tag. 
    If no paragraphs are found, then the original text will be wrapped with line breaks.
    
    :param string $str: 
    :returns: string

*****
Usage
*****

.. include:: usage/text_to_paragraphs.rst

********
Examples
********

.. include:: examples/text_to_paragraphs.rst

********
See Also
********

.. include:: see_also/text_to_paragraphs.rst

