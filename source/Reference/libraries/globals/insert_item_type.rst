.. _finsertitemtype:

################################################
``insert_item_type`` — Insert a new item type.
################################################

:doc:`ItemType-related functions </Reference/packages/Function/Db/ItemType/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/insert_item_type.rst

.. php:function:: insert_item_type($metadata = array(), $elementInfos = array())

    Insert a new item type.
    
    :type $metadata: array
    :param $metadata: Follows the format: <code> array( 'name'        => [string], 'description' => [string] ); </code>
    :type $elementInfos: array
    :param $elementInfos: An array containing element data. Each entry follows one or more of the following formats: <ol> <li>An array containing element metadata</li> <li>An Element object</li> </ol> <code> array( array( 'name' => [(string) name, required], 'description' => [(string) description, optional], 'order' => [(int) order, optional], ), [(Element)], ); </code>
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

