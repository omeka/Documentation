.. _fnav:

##############################################
``nav`` — Create a navigation menu of links.
##############################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/nav.rst

.. php:function:: nav(array $navLinks, $name = null, array $args = array())

    Create a navigation menu of links.
    
    :type $navLinks: array
    :param $navLinks: The array of links for the navigation.
    :type $name: string
    :param $name: Optionally, the name of a filter to pass the links through before using them.
    :type $args: array
    :param $args: Optionally, arguments to pass to the filter
    :returns: Zend_View_Helper_Navigation_Menu The navigation menu object. Can generally be treated simply as a string.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/nav.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/nav.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/nav.rst

