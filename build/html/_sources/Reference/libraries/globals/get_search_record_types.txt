#######################
get_search_record_types
#######################

:doc:`Search-related functions </Reference/packages/Function/Search/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_search_record_types.rst

.. php:function:: get_search_record_types()

    Get all record types that may be indexed and searchable.
    
    Plugins may add record types via the "search_record_types" filter. Thekeys should be the record's class name and the
    respective values shouldbe the human readable and internationalized version of the record type.
    
    These record classes must extend Omeka_Record_AbstractRecord andimplement this search mixin (Mixin_Search).
    
    :returns: array

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_search_record_types.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_search_record_types.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_search_record_types.rst

