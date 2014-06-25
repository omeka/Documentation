.. _flinktocollection:

######################################################
``link_to_collection`` — Get a link to a collection.
######################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_collection.rst

.. php:function:: link_to_collection($text = null, $props = array(), $action = 'show', $collectionObj = null)

    Get a link to a collection.
    
    The only differences from link_to() are that this function will
    automatically use the "current" collection, and will use the collection
    title as the link text.
    
    :type $text: string
    :param $text: text to use for the title of the collection.  Default behavior is to use the name of the collection.
    :type $props: array
    :param $props: Set of attributes to use for the link.
    :type $action: array
    :param $action: The action to link to for the collection.
    :type $collectionObj: array
    :param $collectionObj: Collection record can be passed to this to override the collection object retrieved by get_current_record().
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_collection.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_collection.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_collection.rst

