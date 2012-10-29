---------------
Mixin_Timestamp
---------------

.. php:class:: Mixin_Timestamp

    Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

    Mixin for models that keep added and/or modified timestamps.

    .. php:attr:: _record
    


    .. php:attr:: _addedColumn
    


    .. php:attr:: _modifiedColumn
    


    .. php:method:: __construct(Omeka_Record_AbstractRecord $record, string $addedColumn = added, $modifiedColumn = modified)
    
        Initialize the mixin.
        
        Setting either of the column parameters to null will skip updating thattimestamp. The default column names are 'updated' and 'added'.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param string $addedColumn: Name of the column holding the "added" timestamp.
        :param unknown $modifiedColumn:

    .. php:method:: beforeSave($args)
    
        Before saving a record, set the "updated" timestamp.
        
        :param unknown $args:

    .. php:method:: _setTimestamp(string $column)
    
        Update a timestamp column for the underlying record.
        
        :param string $column: Column to update.