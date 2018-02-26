----------
Collection
----------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Collection

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    A collection and its metadata.

    .. php:attr:: public

        bool

        Whether or not the collection is publicly accessible.

    .. php:attr:: featured

        bool

        Whether or not the collection is featured.

    .. php:attr:: added

        string

        Date the collection was added.

    .. php:attr:: modified

        string

        Date the collection was last modified.

    .. php:attr:: owner_id

        int

        ID for the User that created this collection.

    .. php:attr:: _related

        protected

        Related records.

    .. php:method:: _initializeMixins()

        Initialize the mixins.

    .. php:method:: getProperty($property)

        Get a property about this collection.

        Valid properties for a Collection include:
        * (int) public
        * (int) featured
        * (string) added
        * (string) modified
        * (int) owner_id
        * (int) total_items

        :type $property: string
        :param $property: The property to get, always lowercase.
        :returns: mixed The value of the property

    .. php:method:: totalItems()

        Get the total number of items in this collection.

        :returns: int

    .. php:method:: setAddedBy(User $user)

        Set the user who added the collection.

        Note that this is not to be confused with the collection's "contributors".

        :type $user: User
        :param $user:

    .. php:method:: getResourceId()

        Required by Zend_Acl_Resource_Interface.

        Identifies Collection records as relating to the Collections ACL resource.

        :returns: string

    .. php:method:: hasContributor()

        Return whether the collection has at least 1 contributor element text.

        :returns: bool

    .. php:method:: filterPostData($post)

        Filter the POST data from the form.

        Converts public/featured flags to booleans.

        :type $post: array
        :param $post:
        :returns: array

    .. php:method:: _delete()

        All of the custom code for deleting an collection.

        Delete the element texts for this record.

    .. php:method:: _dissociateItems()

        Set items attached to this collection back to "no collection."

    .. php:method:: beforeSave($args)

        Before-save hook.

        Fire the before-save element texts code.

        :param $args:

    .. php:method:: afterSave($args)

        After-save hook.

        Handle public/private status for search.

        :param $args:

    .. php:method:: getFile()

        Get a representative file for this Collection.

        :returns: File|null
