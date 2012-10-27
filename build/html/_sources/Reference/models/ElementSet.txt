----------
ElementSet
----------

.. php:class:: ElementSet

    Package: :doc:`Record </Reference/packages/Record/index>`

    An element set and its metadata.

    .. php:const:: ITEM_TYPE_NAME
    
    
    
        The name of the item type element set.
        
        This is used wherever it is important to distinguish this special case element set from others.

    .. php:attr:: record_type
    


    .. php:attr:: name
    


    .. php:attr:: description
    


    .. php:attr:: _elementsToSave
    


    .. php:method:: getElements()

    .. php:method:: addElements(array $elements)
    
        Add elements to the element set.
        
        :param array $elements:

    .. php:method:: _buildElementRecord($options)
    
        :param unknown $options:

    .. php:method:: afterSave($args)
    
        :param unknown $args:

    .. php:method:: _delete()
    
        Deletes all the elements associated with an element set.
        
        :returns: void

    .. php:method:: _getNextElementOrder()

    .. php:method:: _validate()