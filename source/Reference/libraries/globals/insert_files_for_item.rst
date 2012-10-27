#####################
insert_files_for_item
#####################

:doc:`Item-related functions </Reference/packages/Function/Db/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_files_for_item.rst

.. php:function:: insert_files_for_item(Item|integer $item, string|Omeka_File_Ingest_AbstractIngest $transferStrategy, array $files, array $options = Array)

    Add files to an item.
    
    :param Item|integer $item: 
    :param string|Omeka_File_Ingest_AbstractIngest $transferStrategy: 
    :param array $files: 
    :param array $options: Available Options:         
    
        .. raw:: html
    
           <ul>
                 <li>'ignore_invalid_files': boolean false by default.  Determine 
                       whether or not to throw exceptions when a file is not valid.
                 </li>
             </ul>
    
    :returns: array

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

