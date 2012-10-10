########
metadata
########

*******
Summary
*******

.. include:: summary/metadata.rst

.. php:function:: metadata(Omeka_Record_AbstractRecord|string $record, mixed $metadata, array $options = Array)

    Return a piece or pieces of metadata for a record.
    
    :param Omeka_Record_AbstractRecord|string $record: The record to get metadata for. If an Omeka_Record_AbstractRecord, that record is used. If a string, that string is used to look up a record in the current view.
    :param mixed $metadata: The metadata to get. If an array is given, this is Element metadata, identified by array('Element Set', 'Element'). If a string, the metadata is a record-specific "property."
    :param array $options: Options for getting the metadata.
    :returns: mixed

*****
Usage
*****

.. include:: usage/metadata.rst

********
Examples
********

.. include:: examples/metadata.rst

********
See Also
********

.. include:: see_also/metadata.rst

