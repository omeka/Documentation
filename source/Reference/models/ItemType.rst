--------
ItemType
--------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: ItemType

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    An item type and its metadata.

    Item types are like specialized element sets that only apply to Items and which can vary between items.

    .. php:const:: ITEM_TYPE_NAME_MIN_CHARACTERS

        Minimum length of an ItemType name.

    .. php:const:: ITEM_TYPE_NAME_MAX_CHARACTERS

        Maximum length of an ItemType name.

    .. php:attr:: name

        string

        Name of this ItemType.

    .. php:attr:: description

        string

        Description for this ItemType.

    .. php:attr:: _related

        protected array

        Records related to an ItemType.

    .. php:method:: getElements()

        Get an array of element objects associated with this item type.

        :returns: array All the Element objects associated with this item type.

    .. php:method:: getItems($count = 10, $recent = true)

        Get an array of Items that have this item type.

        :type $count: int
        :param $count: The maximum number of items to return.
        :type $recent: boolean
        :param $recent: Whether the most recent items should be chosen.
        :returns: array The Item objects associated with the item type.

    .. php:method:: _validate()

        Validate this ItemType.

        The name field must be between 1 and 255 characters and must be unique.

    .. php:method:: filterPostData($post)

        Filter incoming POST data from ItemType form.

        :param $post:

    .. php:method:: _delete()

        Delete all the ItemTypesElements rows joined to this type.

    .. php:method:: afterSave($args)

        After-save hook.

        Save Element records that are associated with this Item Type.

        :param $args:

    .. php:method:: reorderElements($elementOrderingArray)

        Reorder the elements for this type.

        This extracts the ordering for the elements from the form's POST, then
        uses the given ordering to reorder each join record from
        item_types_elements into a new ordering, which is then saved.

        :type $elementOrderingArray: array
        :param $elementOrderingArray: An array of element_id => order pairs

    .. php:method:: addElements($elements = array())

        Add a set of elements to the Item Type.

        :type $elements: array
        :param $elements: Either an array of elements or an array of metadata, where each entry corresponds to a new element to add to the item type.  If an element exists with the same id, it will replace the old element with the new element.

    .. php:method:: addElementById($elementId)

        Add a new element to the item type, giving the Element by its ID.

        :param $elementId:

    .. php:method:: removeElements($elements)

        Remove an array of Elements from this item type

        The elements will not be removed until the object is saved.

        :type $elements: array
        :param $elements: An array of Element objects or element id strings

    .. php:method:: removeElement($element)

        Remove a single Element from this item type.

        The element will not be removed until the object is saved.

        :type $element: Element|string
        :param $element: The element object or the element id.

    .. php:method:: _removeElement($element)

        Immediately remove a single Element from this item type.

        :type $element: Element|string
        :param $element:

    .. php:method:: hasElement($element)

        Determine whether this ItemType has a particular element.

        This method does not handle elements that were added or removed without
        saving the item type object.

        :type $element: Element|string
        :param $element: The element object or the element id.
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
