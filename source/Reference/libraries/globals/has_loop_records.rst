.. _fhaslooprecords:

################
has_loop_records
################

:doc:`Loop-related functions </Reference/packages/Function/View/Loop/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/has_loop_records.rst

.. php:function:: has_loop_records(string $recordsVar)

    Check if records have been set to the view for iteration.
    
    Note that this function will return false if the records variable is set butis an empty array, unlike get_loop_records(), which will return the emptyarray.
    
    :param string $recordsVar: 
    :returns: bool

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/has_loop_records.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/has_loop_records.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/has_loop_records.rst

