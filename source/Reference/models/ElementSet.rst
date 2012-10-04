----------
ElementSet
----------

.. php:class:: ElementSet

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