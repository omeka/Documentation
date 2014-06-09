----
Item
----

.. php:class:: Item

    Package: :doc:`Record </Reference/packages/Record/index>`

    An item and its metadata.

    .. php:attr:: item_type_id
    
        The ID for this Item's ItemType, if any.

    .. php:attr:: collection_id
    
        The ID for this Item's Collection, if any.

    .. php:attr:: featured
    
        Whether this Item is featured.

    .. php:attr:: public
    
        Whether this Item is publicly accessible.

    .. php:attr:: added
    
        The date this Item was added.

    .. php:attr:: modified
    
        The date this Item was last modified.

    .. php:attr:: owner_id
    
        ID of the User who created this Item.

    .. php:attr:: _related
    
        Records related to an Item.

    .. php:attr:: _files
    
        Set of non-persistent File objects to attach to the item.

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

    .. php:method:: getFile(integer $index = 0)
    
        Get a single File associated with this Item, by index.
        
        The default is to get the first file.
        
        :param integer $index: 
        :returns: File

    .. php:method:: getItemTypeElements()
    
        Get a set of Elements associated with this Item's ItemType.
        
        Each one of the Element records that is retrieved should contain all theelement text values associated with it.
        
        :returns: array Element records that are associated with the item type of the item.  This array will be empty if the item does not have an associated type.

    .. php:method:: getProperty(string $property)
    
        Get a property for display.
        
        :param string $property: 
        :returns: mixed

    .. php:method:: beforeSave(array $args)
    
        Before-save hook.
        
        :param array $args:

    .. php:method:: afterSave(array $args)
    
        After-save hook.
        
        :param array $args:

    .. php:method:: _delete()
    
        All of the custom code for deleting an item.

    .. php:method:: _deleteFiles(array $fileIds)
    
        Delete files associated with the item.
        
        If the IDs of specific files are passed in, this will delete only thosefiles (e.g. form submission).  Otherwise, it will delete all filesassociated with the item.
        
        :param array $fileIds: Optional

    .. php:method:: _uploadFiles()
    
        Iterate through the $_FILES array for files that have been uploaded
        to Omeka and attach each of those files to this Item.

    .. php:method:: saveFiles()
    
        Save all the files that have been associated with this item.

    .. php:method:: filterPostData($post)
    
        Filter post data from form submissions.
        
        :param unknown $post: 
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
        
        Generally follows Chicago Manual of Style note format for webpages.Implementers can use the item_citation filter to return a customizedcitation.
        
        :returns: string

    .. php:method:: addFile(File $file)
    
        Associate an unsaved (new) File record with this Item.
        
        These File records will not be persisted in the database until the itemis saved or saveFiles() is invoked.
        
        :param File $file:

    .. php:method:: getResourceId()
    
        Identify Item records as relating to the Items ACL resource.
        
        Required by Zend_Acl_Resource_Interface.
        
        :returns: string

    .. php:method:: _validate()
    
        Validate this item.