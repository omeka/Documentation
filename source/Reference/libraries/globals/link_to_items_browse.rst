.. _flinktoitemsbrowse:

##############################################################################
``link_to_items_browse`` — Get HTML for a link to the browse page for items.
##############################################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to_items_browse.rst

.. php:function:: link_to_items_browse($text, $browseParams = array(), $linkProperties = array())

    Get HTML for a link to the browse page for items.
    
    :type $text: string
    :param $text: Text to display in the link.
    :type $browseParams: array
    :param $browseParams: Any parameters to use to build the browse page URL, e.g. array('collection' => 1) would build items/browse?collection=1 as the URL.
    :type $linkProperties: array
    :param $linkProperties: HTML attributes for the link.
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to_items_browse.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to_items_browse.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to_items_browse.rst

