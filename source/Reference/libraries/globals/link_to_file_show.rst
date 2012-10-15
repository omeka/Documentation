#################
link_to_file_show
#################

*******
Summary
*******

.. include:: summary/link_to_file_show.rst

.. php:function:: link_to_file_show(array $attributes = Array, string $text, File|null $file)

    Return a link to the file metadata page for a particular file.
    
    If no File object is specified, this will determine the file to use throughcontext. The text of the link defaults to
    the DC:Title of the file record,then to the original filename, unless otherwise specified.
    
    :param array $attributes: 
    :param string $text: 
    :param File|null $file: 
    :returns: string

*****
Usage
*****

.. include:: usage/link_to_file_show.rst

********
Examples
********

.. include:: examples/link_to_file_show.rst

********
See Also
********

.. include:: see_also/link_to_file_show.rst

