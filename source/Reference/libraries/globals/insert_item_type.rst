################
insert_item_type
################

:doc:`ItemType-related functions </Reference/packages/Function/Db/ItemType/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_item_type.rst

.. php:function:: insert_item_type(array $metadata = Array, array $elementInfos = Array)

    Insert a new item type.
    
    :param array $metadata: Follows the format:         
    
        .. code-block:: php 
    
    
             array(
               'name'        => [string],
               'description' => [string]
             );
     
    :param array $elementInfos: An array containing element data. Each entry follows one or more of the following formats:         
    
        .. raw:: html
    
           <ol>
               <li>An array containing element metadata</li>
               <li>An Element object</li>
             </ol>
             
    
        .. code-block:: php 
    
    
             array(
               array(
                 'name' => [(string) name, required],
                 'description' => [(string) description, optional],
                 'order' => [(int) order, optional],
               ),
               [(Element)],
             );
     
    :returns: ItemType

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_item_type.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_item_type.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_item_type.rst

