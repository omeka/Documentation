.. _fgetdisplayrecords:

#################################################################
``get_display_records`` — Place HTML for records into an array.
#################################################################

.. versionadded:: 3.2

:doc:`View-related functions </Reference/packages/Function/View/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_display_records.rst

.. php:function:: get_display_records($recordType, $count = 3, $partialPath = null, $partialParams = array(), $query = array())

    Place HTML for records into an array.
    
    :type $recordType: string
    :param $recordType: Type of record to display (Item, Collection, etc.)
    :type $count: int
    :param $count: Maximum number of records to display
    :type $partialPath: string|null
    :param $partialPath: Custom partial to use to display each record; pass null for the default
    :type $partialParams: array
    :param $partialParams: Parameters to pass to the partial
    :type $query: array
    :param $query: Query passed to get_records to get the records to display; default is "random featured"
    :returns: array

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_display_records.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_display_records.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_display_records.rst

