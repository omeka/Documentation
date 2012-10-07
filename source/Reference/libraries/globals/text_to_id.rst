##########
text_to_id
##########

.. php:function:: text_to_id(string $text, string $prepend, string $delimiter = -)

    Convert a word or phrase to dashed format, i.e. Foo Bar => foo-bar.
    
    This is primarily for easy creation of HTML ids within Omeka
    
    <ol>
    <li>convert to lowercase</li>
    <li>Replace whitespace with -</li>
    <li>remove all non-alphanumerics</li>
    <li>remove leading/trailing delimiters</li>
    <li>optionally prepend a piece of text</li>
    </ol>
    
    :param string $text: The text to convert
    :param string $prepend: Another string to prepend to the ID
    :param string $delimiter: The delimiter to use (- by default)
    :returns: string

*****
Usage
*****



********
Examples
********



