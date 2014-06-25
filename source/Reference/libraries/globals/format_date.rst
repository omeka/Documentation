.. _fformatdate:

#############################################################################
``format_date`` — Format a date for output according to the current locale.
#############################################################################

:doc:`Locale-related functions </Reference/packages/Function/Locale/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/format_date.rst

.. php:function:: format_date($date, $format = Zend_Date::DATE_MEDIUM)

    Format a date for output according to the current locale.
    
    :type $date: mixed
    :param $date: Date to format. If an integer, the date is intepreted as a Unix timestamp. If a string, the date is interpreted as an ISO 8601 date.
    :type $format: string
    :param $format: Format to apply. See Zend_Date for possible formats. The default format is the current locale's "medium" format.
    :returns: string

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/format_date.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/format_date.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/format_date.rst

