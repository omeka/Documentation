.. _fmetadata:

###########################################
``metadata`` — Get metadata for a record.
###########################################

:doc:`View-related functions </Reference/packages/Function/View/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/metadata.rst

.. php:function:: metadata($record, $metadata, $options = array())

    Get metadata for a record.
    
    :type $record: Omeka_Record_AbstractRecord|string
    :param $record: The record to get metadata for. If an Omeka_Record_AbstractRecord, that record is used. If a string, that string is used to look up a record in the current view.
    :type $metadata: mixed
    :param $metadata: The metadata to get. If an array is given, this is Element metadata, identified by array('Element Set', 'Element'). If a string, the metadata is a record-specific "property."
    :type $options: array
    :param $options: Options for getting the metadata.
    :returns: mixed

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/metadata.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/metadata.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/metadata.rst

