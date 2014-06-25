.. _fupdateitem:

############################################
``update_item`` — Update an existing item.
############################################

:doc:`Item-related functions </Reference/packages/Function/Db/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/update_item.rst

.. php:function:: update_item($item, $metadata = array(), $elementTexts = array(), $fileMetadata = array())

    Update an existing item.
    
    :type $item: Item|int
    :param $item: Either an Item object or the ID for the item.
    :type $metadata: array
    :param $metadata: Set of options that can be passed to the item.
    :type $elementTexts: array
    :param $elementTexts: Element texts to assign. See insert_item() for details.
    :type $fileMetadata: array
    :param $fileMetadata: File ingest data. See insert_item() for details.
    :returns: Item

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/update_item.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/update_item.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/update_item.rst

