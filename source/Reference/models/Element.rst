-------
Element
-------

.. php:class:: Element

    Package: :doc:`Record </Reference/packages/Record/index>`

    An element and its metadata.

    .. php:attr:: element_set_id
    


    .. php:attr:: order
    


    .. php:attr:: name
    


    .. php:attr:: description
    


    .. php:attr:: comment
    


    .. php:method:: setElementSet(string $elementSetName)
    
        Set the element set for the element.
        
        :param string $elementSetName: 
        :returns: void

    .. php:method:: getElementSet()
    
        Return the ElementSet objection for this element.
        
        :returns: ElementSet

    .. php:method:: setOrder(integer $order)
    
        Set the order of the element within its element set.
        
        :param integer $order: 
        :returns: void

    .. php:method:: setName(string $name)
    
        Set the name of the element.
        
        :param string $name: 
        :returns: void

    .. php:method:: setDescription(string $description)
    
        Set the description for the element.
        
        :param string $description: 
        :returns: void

    .. php:method:: setComment($comment)
    
        :param unknown $comment:

    .. php:method:: setArray(array|string $data)
    
        :param array|string $data: If string, it's the name of the element. Otherwise, array of metadata for the element.  May contain the following keys in the array:         
        
            .. raw:: html
        
               <ul>
                  <li>name</li>
                  <li>description</li>
                  <li>comment</li>
                  <li>order</li>
                  <li>element_set_id</li>
                  <li>element_set</li>
                 </ul>
        
        :returns: void

    .. php:method:: _validate()
    
        Validate the element prior to being saved.
        
        Checks the following criteria:	               
        
        .. raw:: html
        
        <ul>
        	                <li>Name is not empty.</li>
        	                <li>Has a data type.</li>
        	                <li>Has a record type.</li>
        	                <li>Name does not already exist within the given element set.</li>
        	                </ul>

    .. php:method:: _delete()
    
        When deleting this element, delete all ElementText records associated
        with this element.
        
        :returns: void

    .. php:method:: _getElementSetId($elementSetName)
    
        Retrieve the element set ID from the name.
        
        :param unknown $elementSetName: 
        :returns: int

    .. php:method:: _nameIsInSet($elementName, $elementSetId)
    
        Calculate whether the element's name already belongs to the current set.
        
        :param unknown $elementName: 
        :param unknown $elementSetId: 
        :returns: boolean