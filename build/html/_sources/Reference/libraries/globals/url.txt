###
url
###

*******
Summary
*******

.. include:: summary/url.rst

.. php:function:: url(mixed $options = Array, string $route, mixed $queryParams = Array, bool $reset = , bool $encode = 1)

    Return a URL given the provided arguments.
    
    Instantiates view helpers directly because a view may not be registered.
    
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

.. include:: usage/url.rst

********
Examples
********

.. include:: examples/url.rst

********
See Also
********

.. include:: see_also/url.rst

