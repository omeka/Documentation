.. _finsertfilesforitem:

###################################################
``insert_files_for_item`` — Add files to an item.
###################################################

:doc:`Item-related functions </Reference/packages/Function/Db/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_files_for_item.rst

.. php:function:: insert_files_for_item($item, $transferStrategy, $files, $options = array())

    Add files to an item.
    
    :type $item: Item|integer
    :param $item: Item record or ID of item to add files to
    :type $transferStrategy: string|Omeka_File_Ingest_AbstractIngest
    :param $transferStrategy: Strategy to use when ingesting the file. The strings 'Url', 'Filesystem' and 'Upload' correspond to those built-in strategies. Alternatively a strategy object can be passed.
    :type $files: array
    :param $files: Information about the file(s) to ingest. See addFiles() for details
    :type $options: array
    :param $options: Array of options to modify the behavior of the ingest. Available options include: - 'ignore_invalid_files': boolean, false by default. Whether or not to throw exceptions when a file is not valid. - 'ignoreNoFile': (for Upload only) boolean, false by default. Whether to ignore validation errors that occur when an uploaded file is missing, like when a file input is left empty on a form.
    :returns: array The added File records.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_files_for_item.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_files_for_item.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_files_for_item.rst

