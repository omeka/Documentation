################
insert_item_type
################

.. php:function:: insert_item_type(array $metadata = Array, array $elementInfos = Array)

    Insert a new item type.
    
    :param array $metadata: Follows the format: <code> array( 'name'        => [string], 'description' => [string] ); </code>
    :param array $elementInfos: An array containing element data. Each entry follows one or more of the following formats: <ol> <li>An array containing element metadata</li> <li>An Element object</li> </ol> <code> array( array( 'name' => [(string) name, required], 'description' => [(string) description, optional], 'order' => [(int) order, optional], ), [(Element)], ); </code>
    :returns: ItemType

*****
Usage
*****



********
Examples
********



