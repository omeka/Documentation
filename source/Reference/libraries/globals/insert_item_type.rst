################
insert_item_type
################

*******
Summary
*******

.. include:: summary/insert_item_type.rst

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

.. include:: usage/insert_item_type.rst

********
Examples
********

.. include:: examples/insert_item_type.rst

********
See Also
********

.. include:: see_also/insert_item_type.rst

