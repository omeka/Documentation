#################
link_to_items_rss
#################

:doc:`Link-related functions </Reference/packages/Function/View/Body/Navigation/Link/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_items_rss.rst

.. php:function:: link_to_items_rss(string $text, array $params = Array)

    Return a link the the items RSS feed.
    
    :param string $text: The text of the link.
    :param array $params: A set of query string parameters to merge in to the href of the link.  E.g., if this link was clicked on the items/browse?collection=1 page, and array('foo'=>'bar') was passed as this argument, the new URI would be items/browse?collection=1&foo=bar.

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

