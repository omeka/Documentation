.. _fgetrecords:

###########################################################
``get_records`` — Get a set of records from the database.
###########################################################

:doc:`Db-related functions </Reference/packages/Function/Db/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_records.rst

.. php:function:: get_records($recordType, $params = array(), $limit = 10)

    Get a set of records from the database.
    
    :type $recordType: string
    :param $recordType: Type of records to get.
    :type $params: array
    :param $params: Array of search parameters for records.
    :type $limit: integer
    :param $limit: Maximum number of records to return.
    :returns: array An array of result records (of $recordType).

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_records.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_records.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_records.rst

