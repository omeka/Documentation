.. _flinktocollection:

##################
link_to_collection
##################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_collection.rst

.. php:function:: link_to_collection(string $text, array $props, array $action = show, array $collectionObj)

    Return a link to a collection.
    
    :param string $text: text to use for the title of the collection.  Default behavior is to use the name of the collection.
    :param array $props: Set of attributes to use for the link.
    :param array $action: The action to link to for the collection.
    :param array $collectionObj: Collection record can be passed to this to override the collection object retrieved by get_current_record().
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

