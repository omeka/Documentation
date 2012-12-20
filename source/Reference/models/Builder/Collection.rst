------------------
Builder_Collection
------------------

.. php:class:: Builder_Collection

    Package: :doc:`Record\\Builder </Reference/packages/Record/Builder/index>`

    Build a collection.

    .. php:attr:: _recordClass
    


    .. php:attr:: _settableProperties
    


    .. php:attr:: _elementTexts
    


    .. php:method:: setElementTexts(array $elementTexts)
    
        Set the element texts for the collection.
        
        :param array $elementTexts:

    .. php:method:: _addElementTexts()
    
        Add element texts to a record.

    .. php:method:: _replaceElementTexts()
    
        Replace all the element texts for existing element texts.

    .. php:method:: _beforeBuild(Omeka_Record_AbstractRecord $record)
    
        Add elements associated with the collection.
        
        :param Omeka_Record_AbstractRecord $record: The collection record