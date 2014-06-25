-------
Element
-------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Element

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    A metadata element within an element set or item type.

    .. php:attr:: element_set_id

        int

        ID of the ElementSet this Element belongs to.

    .. php:attr:: order

        int

        This Element's order within the parent ElementSet.

    .. php:attr:: name

        string

        A human-readable name

    .. php:attr:: description

        string

        A human-readable description

    .. php:attr:: comment

        string

        A user-generated comment

    .. php:method:: setElementSet($elementSetName)

        Set the parent ElementSet by name.

        :type $elementSetName: string
        :param $elementSetName:

    .. php:method:: getElementSet()

        Return the parent ElementSet object for this element.

        :returns: ElementSet|null

    .. php:method:: setOrder($order)

        Set the order of the element within its element set.

        :type $order: int
        :param $order:

    .. php:method:: setName($name)

        Set the Element's name.

        :type $name: string
        :param $name:

    .. php:method:: setDescription($description)

        Set the Element's description.

        :type $description: string
        :param $description:

    .. php:method:: setComment($comment)

        Set the Element's comment.

        :type $comment: string
        :param $comment:

    .. php:method:: setArray($data)

        Set the data for the Element in bulk.

        * name
        * description
        * comment
        * order
        * element_set_id
        * element_set

        :type $data: array|string
        :param $data: If string, the name of the element. Otherwise, array of metadata for the element.  The array may contain the following keys:

    .. php:method:: _validate()

        Validate the element prior to being saved.

        Checks the following criteria:

        * Name is not empty.
        * Name does not already exist within the given element set.

    .. php:method:: _delete()

        Delete associated records when deleting the Element.

        Cascade delete to all element texts and item type assignments associated
        with the element.

    .. php:method:: _getElementSetId($elementSetName)

        Get an element set ID from a name.

        :param $elementSetName:
        :returns: int

    .. php:method:: _nameIsInSet($elementName, $elementSetId)

        Calculate whether the element's name already belongs to the current set.

        :param $elementName:
        :param $elementSetId:
        :returns: boolean

    .. php:method:: getResourceId()

        Identify Element records as relating to the Elements ACL resource.

        Required by Zend_Acl_Resource_Interface.

        :returns: string
