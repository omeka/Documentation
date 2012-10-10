##################
link_to_collection
##################

*******
Summary
*******

.. include:: summary/link_to_collection.rst

.. php:function:: link_to_collection(string $text, array $props = Array, array $action = show, array $collectionObj)

    Return a link to a collection.
    
    :param string $text: text to use for the title of the collection.  Default behavior is to use the name of the collection.
    :param array $props: Set of attributes to use for the link.
    :param array $action: The action to link to for the collection.
    :param array $collectionObj: Collection record can be passed to this to override the collection object retrieved by get_current_record().
    :returns: string

*****
Usage
*****

.. include:: usage/link_to_collection.rst

********
Examples
********

.. include:: examples/link_to_collection.rst

********
See Also
********

.. include:: see_also/link_to_collection.rst

