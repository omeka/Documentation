#################
insert_collection
#################

*******
Summary
*******

.. include:: summary/insert_collection.rst

.. php:function:: insert_collection(array $metadata = Array)

    Insert a collection
    
    :param array $metadata: Follows the format:         
    
        .. code-block:: php 
    
    
             array(
               'name'        => [string],
               'description' => [string],
               'public'      => [true|false],
               'featured'    => [true|false]
               'collectors'  => [array of string names]
             )
     
    :returns: Collection

*****
Usage
*****

.. include:: usage/insert_collection.rst

********
Examples
********

.. include:: examples/insert_collection.rst

********
See Also
********

.. include:: see_also/insert_collection.rst

