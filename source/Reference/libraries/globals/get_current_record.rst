.. _fgetcurrentrecord:

################################################################
``get_current_record`` — Get the current record from the view.
################################################################

:doc:`Loop-related functions </Reference/packages/Function/View/Loop/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_current_record.rst

.. php:function:: get_current_record($recordVar, $throwException = true)

    Get the current record from the view.
    
    :type $recordVar: string
    :param $recordVar: View variable the current record is stored in.
    :type $throwException: bool
    :param $throwException: Whether to throw an exception if no current record was set. The default is to throw.
    :returns: Omeka_Record_AbstractRecord|false

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_current_record.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_current_record.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_current_record.rst

