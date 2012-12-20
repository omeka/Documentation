.. _finsertcollection:

#################
insert_collection
#################

:doc:`Collection-related functions </Reference/packages/Function/Db/Collection/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_collection.rst

.. php:function:: insert_collection(array $metadata = Array, array $elementTexts = Array)

    Insert a collection
    
    :param array $metadata: Follows the format:         
    
        .. code-block:: php 
    
    
             array(
               'public'      => [true|false],
               'featured'    => [true|false]
             )
     
    :param array $elementTexts: Array of element texts to assign to the collection. This follows the format:         
    
        .. code-block:: php 
    
    
             array(
               [element set name] => array(
                 [element name] => array(
                   array('text' => [string], 'html' => [false|true]),
                   array('text' => [string], 'html' => [false|true])
                  ),
                 [element name] => array(
                   array('text' => [string], 'html' => [false|true]),
                   array('text' => [string], 'html' => [false|true])
                 )
               ),
               [element set name] => array(
                 [element name] => array(
                   array('text' => [string], 'html' => [false|true]),
                   array('text' => [string], 'html' => [false|true])
                 ),
                 [element name] => array(
                   array('text' => [string], 'html' => [false|true]),
                   array('text' => [string], 'html' => [false|true])
                 )
               )
             );
     
    :returns: Collection

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/insert_collection.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/insert_collection.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/insert_collection.rst

