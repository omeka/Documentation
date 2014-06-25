.. _flinktoitemsrss:

############################################################
``link_to_items_rss`` — Get a link the the items RSS feed.
############################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_items_rss.rst

.. php:function:: link_to_items_rss($text = null, $params = array())

    Get a link the the items RSS feed.
    
    :type $text: string
    :param $text: The text of the link.
    :type $params: array
    :param $params: A set of query string parameters to merge in to the href of the link.  E.g., if this link was clicked on the items/browse?collection=1 page, and array('foo'=>'bar') was passed as this argument, the new URI would be items/browse?collection=1&foo=bar.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_items_rss.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_items_rss.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_items_rss.rst

