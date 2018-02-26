----
Item
----

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Item

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    An item and its metadata.

    .. php:attr:: item_type_id

        int

        The ID for this Item's ItemType, if any.

    .. php:attr:: collection_id

        int

        The ID for this Item's Collection, if any.

    .. php:attr:: featured

        int

        Whether this Item is featured.

    .. php:attr:: public

        int

        Whether this Item is publicly accessible.

    .. php:attr:: added

        string

        The date this Item was added.

    .. php:attr:: modified

        string

        The date this Item was last modified.

    .. php:attr:: owner_id

        int

        ID of the User who created this Item.

    .. php:attr:: _related

        protected array

        Records related to an Item.

    .. php:method:: _initializeMixins()

        Initialize the mixins.

    .. php:method:: getCollection()

        Get this Item's Collection, if any.

        :returns: Collection|null

    .. php:method:: getItemType()

        Get the ItemType record associated with this Item.

        :returns: ItemType|null

    .. php:method:: getFiles()

        Get the set of File records associated with this Item.

        :returns: array

    .. php:method:: getFile($index = 0)

        Get a single File associated with this Item, by index.

        The default is to get the first file.

        :type $index: int
        :param $index:
        :returns: File

    .. php:method:: getItemTypeElements()

        Get a set of Elements associated with this Item's ItemType.

        Each one of the Element records that is retrieved should contain all the
        element text values associated with it.

        :returns: array Element records that are associated with the item type of the item.  This array will be empty if the item does not have an associated type.

    .. php:method:: getProperty($property)

        Get a property for display.

        :type $property: string
        :param $property:
        :returns: mixed

    .. php:method:: beforeSave($args)

        Before-save hook.

        :type $args: array
        :param $args:

    .. php:method:: afterSave($args)

        After-save hook.

        :type $args: array
        :param $args:

    .. php:method:: _delete()

        All of the custom code for deleting an item.

    .. php:method:: _deleteFiles($fileIds = array())

        Delete files associated with the item.

        If the IDs of specific files are passed in, this will delete only those
        files (e.g. form submission).  Otherwise, it will delete all files
        associated with the item.

        :type $fileIds: array
        :param $fileIds: Optional

    .. php:method:: _uploadFiles()

        Iterate through the $_FILES array for files that have been uploaded
        to Omeka and attach each of those files to this Item.

    .. php:method:: saveFiles()

        Save all the files that have been associated with this item.

    .. php:method:: filterPostData($post)

        Filter post data from form submissions.

        :param $post:
        :returns: array Clean post data

    .. php:method:: fileCount()

        Get the number of files assigned to this item.

        :returns: int

    .. php:method:: previous()

        Get the previous Item in the database.

        :returns: Item|false

    .. php:method:: next()

        Get the next Item in the database.

        :returns: Item|false

    .. php:method:: hasThumbnail()

        Determine whether or not the Item has a File with a thumbnail image
        (or any derivative image).

        :returns: bool

    .. php:method:: getCitation()

        Return a valid citation for this item.

        Generally follows Chicago Manual of Style note format for webpages.
        Implementers can use the item_citation filter to return a customized
        citation.

        :returns: string

    .. php:method:: addFile(File $file)

        Associate an unsaved (new) File record with this Item.

        These File records will not be persisted in the database until the item is
        saved or saveFiles() is invoked.

        :type $file: File
        :param $file:

    .. php:method:: getResourceId()

        Identify Item records as relating to the Items ACL resource.

        Required by Zend_Acl_Resource_Interface.

        :returns: string

    .. php:method:: _validate()

        Validate this item.
