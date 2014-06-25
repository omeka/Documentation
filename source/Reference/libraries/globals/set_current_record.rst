.. _fsetcurrentrecord:

##########################################################################
``set_current_record`` — Set a record to the view as the current record.
##########################################################################

:doc:`Loop-related functions </Reference/packages/Function/View/Loop/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/set_current_record.rst

.. php:function:: set_current_record($recordVar, Omeka_Record_AbstractRecord $record, $setPreviousRecord = false)

    Set a record to the view as the current record.
    
    :type $recordVar: string
    :param $recordVar: View variable to store the current record in.
    :type $record: Omeka_Record_AbstractRecord
    :param $record:
    :type $setPreviousRecord: bool
    :param $setPreviousRecord: Whether to store the previous "current" record, if any. The default is to not store the previous record.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/set_current_record.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/set_current_record.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/set_current_record.rst

