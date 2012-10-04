---------------------
Omeka_Record_Iterator
---------------------

.. php:class:: Omeka_Record_Iterator

    .. php:attr:: _records
    


    .. php:attr:: _view
    


    .. php:attr:: _currentRecordVar
    


    .. php:method:: __construct(array $records, null|Zend_View_Abstract $view, null|string $currentRecordVar)
    
        Construct the record iterator.
        
        :param array $records: 
        :param null|Zend_View_Abstract $view: 
        :param null|string $currentRecordVar:

    .. php:method:: rewind()

    .. php:method:: current()
    
        Return the current record, setting it to the view if applicable.

    .. php:method:: key()

    .. php:method:: next()
    
        Release the previous record and advance the pointer to the next one.

    .. php:method:: valid()