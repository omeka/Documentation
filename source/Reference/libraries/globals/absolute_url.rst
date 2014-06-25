.. _fabsoluteurl:

#########################################
``absolute_url`` — Get an absolute URL.
#########################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/absolute_url.rst

.. php:function:: absolute_url($options = array(), $route = null, $queryParams = array(), $reset = false, $encode = true)

    Get an absolute URL.
    
    This is necessary because Zend_View_Helper_Url returns relative URLs,
    though absolute URLs are required in some contexts. Instantiates view
    helpers directly because a view may not be registered.
    
    :type $options: mixed
    :param $options: If a string is passed it is treated as an Omeka-relative link. So, passing 'items' would create a link to the items page. If an array is passed (or no argument given), it is treated as options to be passed to Omeka's routing system.
    :type $route: string
    :param $route: The route to use if an array is passed in the first argument.
    :type $queryParams: mixed
    :param $queryParams: A set of query string parameters to append to the URL
    :type $reset: bool
    :param $reset: Whether Omeka should discard the current route when generating the URL.
    :type $encode: bool
    :param $encode: Whether the URL should be URL-encoded
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/absolute_url.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/absolute_url.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/absolute_url.rst

