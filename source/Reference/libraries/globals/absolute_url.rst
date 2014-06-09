.. _fabsoluteurl:

############
absolute_url
############

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/absolute_url.rst

.. php:function:: absolute_url(mixed $options, string $route, mixed $queryParams, bool $reset = , bool $encode = 1)

    Return an absolute URL.
    
    This is necessary because Zend_View_Helper_Url returns relative URLs, thoughabsolute URLs are required in some contexts. Instantiates view helpersdirectly because a view may not be registered.
    
    :param mixed $options:         
    
        .. raw:: html
    
           <ul>
                  <li> If a string is passed it is treated as an Omeka-relative link. So, passing 'items' would create a link to the items page.</li>
                  <li> (Advanced) If an array is passed (or no argument given), it is treated as options to be passed to Omeka's routing system.</li>
             </ul>
    
    :param string $route: The route to use if an array is passed in the first argument.
    :param mixed $queryParams: A set of query string parameters to append to the URL
    :param bool $reset: Whether Omeka should discard the current route when generating the URL.
    :param bool $encode: Whether the URL should be URL-encoded
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

