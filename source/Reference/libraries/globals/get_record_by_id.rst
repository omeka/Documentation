.. _fgetrecordbyid:

################################################
``get_record_by_id`` — Get a record by its ID.
################################################

:doc:`Db-related functions </Reference/packages/Function/Db/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_record_by_id.rst

.. php:function:: get_record_by_id($modelName, $recordId)

    Get a record by its ID.
    
    :type $modelName: string
    :param $modelName: Name of the Record model being looked up (e.g., 'Item')
    :type $recordId: int
    :param $recordId: The ID of the specific record to find.
    :returns: Omeka_Record_AbstractRecord|null The record, or null if it cannot be found.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_record_by_id.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_record_by_id.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_record_by_id.rst

