#######################
get_search_record_types
#######################

*******
Summary
*******

.. include:: summary/get_search_record_types.rst

.. php:function:: get_search_record_types()

    Get all record types that may be indexed and searchable.
    
    Plugins may add record types via the "search_record_types" filter. Thekeys should be the record's class name and the
    respective values shouldbe the human readable and internationalized version of the record type.
    
    These record classes must extend Omeka_Record_AbstractRecord andimplement this search mixin (Mixin_Search).
    
    :returns: array

*****
Usage
*****

.. include:: usage/get_search_record_types.rst

********
Examples
********

.. include:: examples/get_search_record_types.rst

********
See Also
********

.. include:: see_also/get_search_record_types.rst

