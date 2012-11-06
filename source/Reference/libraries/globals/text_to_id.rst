.. _ftexttoid:

##########
text_to_id
##########

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/text_to_id.rst

.. php:function:: text_to_id($text, $prepend, $delimiter = -)

    Convert a word or phrase to dashed format, i.e. Foo Bar => foo-bar.
    
    This is primarily for easy creation of HTML ids within Omeka
    
    	               
    
    .. raw:: html
    
    <ol>
    	                 <li>convert to lowercase</li>
    	                 <li>Replace whitespace with -</li>
    	                 <li>remove all non-alphanumerics</li>
    	                 <li>remove leading/trailing delimiters</li>
    	                 <li>optionally prepend a piece of text</li>
    	                </ol>
    
    :param unknown $text: 
    :param unknown $prepend: 
    :param unknown $delimiter:

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

