--------------------------------------
Omeka_Record_Api_AbstractRecordAdapter
--------------------------------------

.. php:class:: Omeka_Record_Api_AbstractRecordAdapter

    Package: :doc:`Record\\Api </Reference/packages/Record/Api/index>`

    .. php:attr:: _elementsCache
    


    .. php:attr:: _elementSetsCache
    


    .. php:method:: setPostData(Omeka_Record_AbstractRecord $record, mixed $data)
    
        Set data to a record during a POST request.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param mixed $data:

    .. php:method:: setPutData(Omeka_Record_AbstractRecord $record, mixed $data)
    
        Set data to a record during a PUT request.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param mixed $data:

    .. php:method:: getElementTextRepresentations(Omeka_Record_AbstractRecord $record)
    
        Get representations of element texts belonging to a record.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: array

    .. php:method:: setElementTextData(Omeka_Record_AbstractRecord $record, mixed $data)
    
        Set element text data to a record.
        
        The record must initialize the ElementText mixin.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param mixed $data:

    .. php:method:: getTagRepresentations(Omeka_Record_AbstractRecord $record)
    
        Get representations of tags belonging to a record.
        
        The record must initialize the Tag mixin.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: array

    .. php:method:: setTagData(Omeka_Record_AbstractRecord $record, mixed $data)
    
        Set tag data to a record.
        
        The record must initialize the Tag mixin.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param mixed $data:

    .. php:method:: getResourceUrl(string $uri)
    
        Get the absolute URL to the passed resource.
        
        :param string $uri: The full resource URI
        :returns: string

    .. php:method:: getDate(string $date)
    
        Format a date string as an ISO 8601 date, UTC timezone.
        
        :param string $date: 
        :returns: string

    .. php:method:: _getUnfilteredElementTextRepresentations(Omeka_Record_AbstractRecord $record)
    
        Get unfiltered representations of element texts belonging to a record.
        
        Note the HTML flag in the representation. This indicates to the consumerthat the representation is unfiltered.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: array

    .. php:method:: _getFilteredElementTextRepresentations(Omeka_Record_AbstractRecord $record)
    
        Get filtered representations of element texts belonging to a record.
        
        Note the lack of the HTML flag in the representation. This indicates tothe consumer that the representation is filtered through thedisplay_elements and array('Display',...) element texts filters.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: array

    .. php:method:: getRepresentation(Omeka_Record_AbstractRecord $record)
    
        Get the REST representation of a record.
        
        :param Omeka_Record_AbstractRecord $record: