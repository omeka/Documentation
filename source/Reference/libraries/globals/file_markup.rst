.. _ffilemarkup:

################################################
``file_markup`` — Get HTML for a set of files.
################################################

:doc:`File-related functions </Reference/packages/Function/View/File/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/file_markup.rst

.. php:function:: file_markup($files, array $options = array(), $wrapperAttributes = array('class' => 'item-file'))

    Get HTML for a set of files.
    
    :type $files: File
    :param $files: A file record or an array of File records to display.
    :type $options: array
    :param $options: Options to customize display for different file types.
    :type $wrapperAttributes: array
    :param $wrapperAttributes: Attributes HTML attributes for the div that wraps each displayed file. If empty or null, this will not wrap the displayed file in a div.
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/file_markup.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/file_markup.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/file_markup.rst

