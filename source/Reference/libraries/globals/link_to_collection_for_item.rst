.. _flinktocollectionforitem:

###########################################################################################
``link_to_collection_for_item`` — Get a link to the collection to which the item belongs.
###########################################################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_collection_for_item.rst

.. php:function:: link_to_collection_for_item($text = null, $props = array(), $action = 'show')

    Get a link to the collection to which the item belongs.
    
    The default text displayed for this link will be the name of the
    collection,
    but that can be changed by passing a string argument.
    
    :type $text: string|null
    :param $text: Text for the link.
    :type $props: array
    :param $props: HTML attributes for the <a> tag.
    :type $action: string
    :param $action: 'show' by default.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_collection_for_item.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_collection_for_item.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_collection_for_item.rst

