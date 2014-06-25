----------
ElementSet
----------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: ElementSet

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    An element set and its metadata.

    .. php:const:: ITEM_TYPE_NAME

        The name of the item type element set.

        This is used wherever it is important to distinguish this special case element set from others.

    .. php:attr:: record_type

        string

        Type of record this set applies to.

    .. php:attr:: name

        string

        Name for the element set.

    .. php:attr:: description

        string

        Description for the element set.

    .. php:attr:: _elementsToSave

        protected array

        Child Element records to save when saving this set.

    .. php:method:: getElements()

        Get the Elements that are in this set.

        :returns: array

    .. php:method:: addElements($elements)

        Add elements to the element set.

        :type $elements: array
        :param $elements:

    .. php:method:: _buildElementRecord($options)

        Create a new Element record with the given data.

        :type $options: array
        :param $options: Data to set on the Element.
        :returns: Element

    .. php:method:: afterSave($args)

        After-save hook.

        Save the $_elementsToSave and set their orders.

        :param $args:

    .. php:method:: _delete()

        Delete all the elements associated with an element set.

        :returns: void

    .. php:method:: _getNextElementOrder()

        Get an order value to place an Element at the end of this set.

        :returns: int

    .. php:method:: _validate()

        Validate the element set.

        Tests that name is non-empty and unique.

    .. php:method:: getResourceId()

        Identify ElementSet records as relating to the ElementSets ACL resource.

        Required by Zend_Acl_Resource_Interface.

        :returns: string
