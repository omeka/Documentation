--------
ItemType
--------

.. php:class:: ItemType

    Package: :doc:`Record </Reference/packages/Record/index>`

    An item type and its metadata.

    .. php:attr:: name
    


    .. php:attr:: description
    


    .. php:attr:: _related
    


    .. php:attr:: _elementsToSave
    


    .. php:attr:: _elementsToRemove
    


    .. php:method:: getElements()
    
        Returns an array of element objects associated with this item type.
        
        :returns: array The array of element objects associated with this item type.

    .. php:method:: getItems(int $count = 10, boolean $recent = 1)
    
        Returns an array of item objects that have this item type.
        
        :param int $count: The maximum number of items to return.
        :param boolean $recent:  Whether or not the items are recent.
        :returns: array The items associated with the item type.

    .. php:method:: _validate()
    
        Current validation rules for Type
        
        1) 'Name' field can't be blank2) 'Name' field must be unique
        
        :returns: void

    .. php:method:: filterPostData($post)
    
        Filter incoming POST data from ItemType form.
        
        :param unknown $post: 
        :returns: void

    .. php:method:: _delete()
    
        Delete all the ItemTypesElements joins
        
        :returns: void

    .. php:method:: afterSave($args)
    
        Save Element records that are associated with this Item Type.
        
        :param unknown $args: 
        :returns: void

    .. php:method:: reorderElements(Array $elementOrderingArray)
    
        This extracts the ordering for the elements from the form's POST, then uses
        the given ordering to resort the join records from item_types_elements into
        a new ordering, which is then saved.
        
        :param Array $elementOrderingArray: An array of numbers representing
        :returns: void

    .. php:method:: addElements(array $elements = Array)
    
        Add a set of elements to the Item Type.
        
        :param array $elements: Either an array of elements or an array of metadata, where each entry corresponds to a new element to add to the item type.  If an element exists with the same id, it will replace the old element with the new element.
        :returns: void

    .. php:method:: addElementById($elementId)
    
        Adds a new element to the item type by the id of the element
        
        :param unknown $elementId: 
        :returns: void

    .. php:method:: removeElements(Array $elements)
    
        Removes an array of Elements from this item type
        The element will not be removed until the object is saved.
        
        :param Array $elements: An array of Element objects or element id strings
        :returns: void

    .. php:method:: removeElement(Element|string $element)
    
        Remove a single Element from this item type.
        The element will not be removed until the object is saved.
        
        :param Element|string $element: The element object or the element id.
        :returns: void

    .. php:method:: _removeElement(Element|string $element)
    
        Removes a single Element from this item type.  It removes it immediately.
        
        :param Element|string $element: 
        :returns: void

    .. php:method:: hasElement(Element|string $element)
    
        Determines whether a saved version of the item type has an element.
        It does not correctly determine the presence of elements that were added or
        removed without saving the item type object.
        
        :param Element|string $element:  The element object or the element id.
        :returns: boolean

    .. php:method:: totalItems()
    
        Determines the total number of items that have this item type.
        
        :returns: int The total number of items that have this item type.

    .. php:method:: getItemTypeElementSet()
    
        Returns the 'Item Type' element set.
        
        :returns: ElementSet