######
option
######

:doc:`Option-related functions </Reference/packages/Function/View/Option/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/option.rst

.. php:function:: option(string $name)

    Return the value of a particular site setting.  This can be used to display
    any option that would be retrieved with get_option().
    
    Content for any specific option can be filtered by using a filter named'display_option_(option)' where (option) is the name of the option, e.g.'display_option_site_title'.
    
    :param string $name: The name of the option
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/option.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/option.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/option.rst

