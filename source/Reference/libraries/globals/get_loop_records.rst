.. _fgetlooprecords:

#################################################################
``get_loop_records`` — Get records from the view for iteration.
#################################################################

:doc:`Loop-related functions </Reference/packages/Function/View/Loop/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_loop_records.rst

.. php:function:: get_loop_records($recordsVar, $throwException = true)

    Get records from the view for iteration.
    
    Note that this function will return an empty array if it is set to the
    records variable. Use has_loop_records() to check if records exist.
    
    :type $recordsVar: string
    :param $recordsVar: The name of the variable the records are stored in.
    :type $throwException: boolean
    :param $throwException: Whether to throw an exception if the $recordsVar is unset. Default is to throw.
    :returns: array|bool

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_loop_records.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_loop_records.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_loop_records.rst

