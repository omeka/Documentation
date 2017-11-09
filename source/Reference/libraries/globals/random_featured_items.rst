.. _frandomfeatureditems:

#################################################################
``random_featured_items`` — Get HTML for random featured items.
#################################################################

:doc:`Item-related functions </Reference/packages/Function/View/Item/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/random_featured_items.rst

.. php:function:: random_featured_items($count = 5, $hasImage = null)

    Get HTML for random featured items.
    
    :type $count: int
    :param $count: Maximum number of items to show.
    :type $hasImage: bool
    :param $hasImage: Whether or not the featured items must have images associated. If null, as default, all featured items can appear, whether or not they have files. If true, only items with files will appear, and if false, only items without files will appear.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/random_featured_items.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/random_featured_items.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/random_featured_items.rst

