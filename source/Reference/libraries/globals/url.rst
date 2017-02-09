.. _furl:

###################################################
``url`` — Get a URL given the provided arguments.
###################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/url.rst

.. php:function:: url($options = array(), $route = null, $queryParams = array(), $reset = false, $encode = true)

    Get a URL given the provided arguments.
    
    Instantiates view helpers directly because a view may not be registered.
    
    :type $options: mixed
    :param $options: If a string is passed it is treated as an Omeka-relative link. So, passing 'items' would create a link to the items page. If an array is passed (or no argument given), it is treated as options to be passed to Omeka's routing system. Note that in the Url Helper, if the first argument is a string, the second argument, not the third, is the queryParams
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

.. include:: /Reference/libraries/globals/usage/url.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/url.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/url.rst

