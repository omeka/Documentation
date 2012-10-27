----------------
Builder_ItemType
----------------

.. php:class:: Builder_ItemType

    Package: :doc:`Record\\Builder </Reference/packages/Record/Builder/index>`

    Build an item type.

    .. php:attr:: _recordClass
    


    .. php:attr:: _settableProperties
    


    .. php:attr:: _elements
    


    .. php:method:: setElements(array $elementMetadata)
    
        Set the elements that will be attached to the built ItemType record.
        
        :param array $elementMetadata: 
        :returns: void

    .. php:method:: _beforeBuild()
    
        Add elements to be associated with the Item Type.