###########
format_date
###########

:doc:`Text-related functions </Reference/packages/Function/Text/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/format_date.rst

.. php:function:: format_date(mixed $date, string $format = FFF)

    Format a date for output according to the current locale.
    
    :param mixed $date: Date to format. If an integer, the date is intepreted as a Unix timestamp. If a string, the date is interpreted as an ISO 8601 date.
    :param string $format: Format to apply. See Zend_Date for possible formats. The default format is the current locale's "medium" format.
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

