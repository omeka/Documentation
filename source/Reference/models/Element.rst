-------
Element
-------

.. php:class:: Element

    Package: :doc:`Record </Reference/packages/Record/index>`

    A metadata element within an element set or item type.

    .. php:attr:: element_set_id
    
        ID of the ElementSet this Element belongs to.

    .. php:attr:: order
    
        This Element's order within the parent ElementSet.

    .. php:attr:: name
    
        A human-readable name

    .. php:attr:: description
    
        A human-readable description

    .. php:attr:: comment
    
        A user-generated comment

    .. php:method:: setElementSet(string $elementSetName)
    
        Set the parent ElementSet by name.
        
        :param string $elementSetName:

    .. php:method:: getElementSet()
    
        Return the parent ElementSet object for this element.
        
        :returns: ElementSet|null

    .. php:method:: setOrder(int $order)
    
        Set the order of the element within its element set.
        
        :param int $order:

    .. php:method:: setName(string $name)
    
        Set the Element's name.
        
        :param string $name:

    .. php:method:: setDescription(string $description)
    
        Set the Element's description.
        
        :param string $description:

    .. php:method:: setComment(string $comment)
    
        Set the Element's comment.
        
        :param string $comment:

    .. php:method:: setArray(array|string $data)
    
        Set the data for the Element in bulk.
        
        * name* description* comment* order* element_set_id* element_set
        
        :param array|string $data: If string, the name of the element. Otherwise, array of metadata for the element.  The array may contain the following keys:

    .. php:method:: _validate()
    
        Validate the element prior to being saved.
        
        Checks the following criteria:
        
        * Name is not empty.
        * Name does not already exist within the given element set.

    .. php:method:: _delete()
    
        Delete associated records when deleting the Element.
        
        Cascade delete to all element texts and item type assignments associated with the element.

    .. php:method:: _getElementSetId($elementSetName)
    
        Get an element set ID from a name.
        
        :param unknown $elementSetName: 
        :returns: int

    .. php:method:: _nameIsInSet($elementName, $elementSetId)
    
        Calculate whether the element's name already belongs to the current set.
        
        :param unknown $elementName: 
        :param unknown $elementSetId: 
        :returns: boolean

    .. php:method:: getResourceId()
    
        Identify Element records as relating to the Elements ACL resource.
        
        Required by Zend_Acl_Resource_Interface.
        
        :returns: string