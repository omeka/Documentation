------------------
Builder_ElementSet
------------------

.. php:class:: Builder_ElementSet

    Build an element set.

    .. php:attr:: _settableProperties
    


    .. php:attr:: _recordClass
    


    .. php:attr:: _elementInfo
    


    .. php:method:: setElements(array $elements)
    
        Set the elements to add to the element set.
        
        :param array $elements:

    .. php:method:: setRecordMetadata(string|array $metadata)
    
        Overrides setRecordMetadata() to allow giving the name of the element as
        a string.
        
        :param string|array $metadata:

    .. php:method:: _beforeBuild()
    
        Add elements to be associated with the element set.