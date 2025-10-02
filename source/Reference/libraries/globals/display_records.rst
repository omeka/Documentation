.. _fdisplayrecords:

#############################################
``display_records`` — Get HTML for records.
#############################################

.. versionadded:: 3.2

:doc:`View-related functions </Reference/packages/Function/View/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/display_records.rst

.. php:function:: display_records($recordType, $count = 3, $partialPath = null, $partialParams = array(), $query = array())

    Get HTML for records.
    
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
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/display_records.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/display_records.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/display_records.rst

