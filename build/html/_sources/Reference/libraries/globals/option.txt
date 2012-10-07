######
option
######

.. php:function:: option($name)

    Return the value of a particular site setting.  This can be used to display
    any option that would be retrieved with get_option().
    
    Content for any specific option can be filtered by using a filter named
    'display_option_(option)' where (option) is the name of the option, e.g.
    'display_option_site_title'.
    
    :param unknown $name: 
    :returns: string

*****
Usage
*****



********
Examples
********



