--------
ItemType
--------

.. php:class:: ItemType

    Package: :doc:`Record </Reference/packages/Record/index>`

    An item type and its metadata.
    
    Item types are like specialized element sets that only apply to Items andwhich can vary between items.

    .. php:const:: ITEM_TYPE_NAME_MIN_CHARACTERS
    
    
    
        Minimum length of an ItemType name.

    .. php:const:: ITEM_TYPE_NAME_MAX_CHARACTERS
    
    
    
        Maximum length of an ItemType name.

    .. php:attr:: name
    
        Name of this ItemType.

    .. php:attr:: description
    
        Description for this ItemType.

    .. php:attr:: _related
    
        Records related to an ItemType.

    .. php:attr:: _elementsToSave
    
        New Elements to be added for this type.

    .. php:attr:: _elementsToRemove
    
        Elements to be removed from this type.

    .. php:method:: getElements()
    
        Get an array of element objects associated with this item type.
        
        :returns: array All the Element objects associated with this item type.

    .. php:method:: getItems(int $count = 10, boolean $recent = 1)
    
        Get an array of Items that have this item type.
        
        :param int $count: The maximum number of items to return.
        :param boolean $recent:  Whether the most recent items should be chosen.
        :returns: array The Item objects associated with the item type.

    .. php:method:: _validate()
    
        Validate this ItemType.
        
        The name field must be between 1 and 255 characters and must be unique.

    .. php:method:: filterPostData($post)
    
        Filter incoming POST data from ItemType form.
        
        :param unknown $post:

    .. php:method:: _delete()
    
        Delete all the ItemTypesElements rows joined to this type.

    .. php:method:: afterSave($args)
    
        After-save hook.
        
        Save Element records that are associated with this Item Type.
        
        :param unknown $args:

    .. php:method:: reorderElements(array $elementOrderingArray)
    
        Reorder the elements for this type.
        
        This extracts the ordering for the elements from the form's POST, then usesthe given ordering to reorder each join record from item_types_elements intoa new ordering, which is then saved.
        
        :param array $elementOrderingArray: An array of element_id => order pairs

    .. php:method:: addElements(array $elements)
    
        Add a set of elements to the Item Type.
        
        :param array $elements: Either an array of elements or an array of metadata, where each entry corresponds to a new element to add to the item type.  If an element exists with the same id, it will replace the old element with the new element.

    .. php:method:: addElementById($elementId)
    
        Add a new element to the item type, giving the Element by its ID.
        
        :param unknown $elementId:

    .. php:method:: removeElements(array $elements)
    
        Remove an array of Elements from this item type
        
        The elements will not be removed until the object is saved.
        
        :param array $elements: An array of Element objects or element id strings

    .. php:method:: removeElement(Element|string $element)
    
        Remove a single Element from this item type.
        
        The element will not be removed until the object is saved.
        
        :param Element|string $element: The element object or the element id.

    .. php:method:: _removeElement(Element|string $element)
    
        Immediately remove a single Element from this item type.
        
        :param Element|string $element:

    .. php:method:: hasElement(Element|string $element)
    
        Determine whether this ItemType has a particular element.
        
        This method does not handle elements that were added orremoved without saving the item type object.
        
        :param Element|string $element:  The element object or the element id.
        :returns: bool

    .. php:method:: totalItems()
    
        Get the total number of items that have this item type.
        
        :returns: int The total number of items that have this item type.

    .. php:method:: getItemTypeElementSet()
    
        Get the 'Item Type' element set.
        
        :returns: ElementSet

    .. php:method:: getResourceId()
    
        Identify ItemType records as relating to the ItemTypes ACL resource.
        
        Required by Zend_Acl_Resource_Interface.
        
        :returns: string