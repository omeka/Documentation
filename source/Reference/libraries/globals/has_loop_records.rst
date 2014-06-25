.. _fhaslooprecords:

##################################################################################
``has_loop_records`` — Check if records have been set to the view for iteration.
##################################################################################

:doc:`Loop-related functions </Reference/packages/Function/View/Loop/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/has_loop_records.rst

.. php:function:: has_loop_records($recordsVar)

    Check if records have been set to the view for iteration.
    
    Note that this function will return false if the records variable is set
    but is an empty array, unlike get_loop_records(), which will return the
    empty array.
    
    :type $recordsVar: string
    :param $recordsVar: View variable to check.
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

