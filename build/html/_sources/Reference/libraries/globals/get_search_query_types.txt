######################
get_search_query_types
######################

*******
Summary
*******

.. include:: summary/get_search_query_types.rst

.. php:function:: get_search_query_types()

    Get all available search query types.
    
    Plugins may add query types via the "search_query_types" filter. The keysshould be the type's GET query value and
    the respective values should be thehuman readable and internationalized version of the query type.
    
    Plugins that add a query type must modify the select object via the"search_sql" hook to account for whatever custom
    search strategy theyimplement.
    
    :returns: array

*****
Usage
*****

.. include:: usage/get_search_query_types.rst

********
Examples
********

.. include:: examples/get_search_query_types.rst

********
See Also
********

.. include:: see_also/get_search_query_types.rst

