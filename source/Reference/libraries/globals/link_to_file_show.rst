.. _flinktofileshow:

#####################################################################################
``link_to_file_show`` — Get a link to the file metadata page for a particular file.
#####################################################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_file_show.rst

.. php:function:: link_to_file_show($attributes = array(), $text = null, $file = null)

    Get a link to the file metadata page for a particular file.
    
    If no File object is specified, this will determine the file to use
    through context. The text of the link defaults to the DC:Title of the file
    record,
    then to the original filename, unless otherwise specified.
    
    :type $attributes: array
    :param $attributes:
    :type $text: string
    :param $text:
    :type $file: File|null
    :param $file:
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_file_show.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_file_show.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_file_show.rst

