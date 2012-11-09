----
Item
----

.. php:class:: Item

    Package: :doc:`Record </Reference/packages/Record/index>`

    An item and its metadata.

    .. php:attr:: item_type_id
    


    .. php:attr:: collection_id
    


    .. php:attr:: featured
    


    .. php:attr:: public
    


    .. php:attr:: added
    


    .. php:attr:: modified
    


    .. php:attr:: owner_id
    


    .. php:attr:: _related
    


    .. php:attr:: _files
    


    .. php:method:: _initializeMixins()

    .. php:method:: getCollection()
    
        :returns: null|Collection

    .. php:method:: getItemType()
    
        Retrieve the ItemType record associated with this Item.
        
        :returns: ItemType|null

    .. php:method:: getFiles()
    
        Retrieve the set of File records associated with this Item.
        
        :returns: array

    .. php:method:: getItemTypeElements()
    
        Retrieve a set of elements associated with the item type of the item.
        
        Each one of the Element records that is retrieved should contain all theelement text values associated with it.
        
        :returns: array Element records that are associated with the item type of the item.  This array will be empty if the item does not have an associated type.

    .. php:method:: getProperty(string $property)
    
        Get a property for display.
        
        :param string $property: 
        :returns: mixed

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: afterSave($args)
    
        Logic for after the record has been saved.
        
        :param unknown $args:

    .. php:method:: _delete()
    
        All of the custom code for deleting an item.
        
        :returns: void

    .. php:method:: _deleteFiles(array $fileIds = Array)
    
        Delete files associated with the item.
        
        If the IDs of specific files are passed in, this will delete only thosefiles (e.g. form submission).  Otherwise, it will delete all filesassociated with the item.
        
        :param array $fileIds: Optional
        :returns: void

    .. php:method:: _uploadFiles()
    
        Iterate through the $_FILES array for files that have been uploaded
        to Omeka and attach each of those files to this Item.
        
        :returns: void

    .. php:method:: saveFiles()
    
        Save all the files that have been associated with this item.
        
        :returns: boolean

    .. php:method:: filterPostData($post)
    
        Filter post data from form submissions.
        
        :param unknown $post: 
        :returns: array Clean post data

    .. php:method:: fileCount()
    
        Retrieve the number of files assigned to this item.
        
        :returns: boolean

    .. php:method:: previous()
    
        Retrieve the previous Item in the database.
        
        :returns: Item|false

    .. php:method:: next()
    
        Retrieve the next Item in the database.
        
        :returns: Item|false

    .. php:method:: hasThumbnail()
    
        Determine whether or not the Item has a File with a thumbnail image
        (or any derivative image).
        
        :returns: boolean

    .. php:method:: getCitation()
    
        Return a valid citation for this item.
        
        Generally follows Chicago Manual of Style note format for webpages.Implementers can use the item_citation filter to return a customizedcitation.
        
        :returns: string

    .. php:method:: addFile(File $file)
    
        Associate an unsaved (new) File record with this Item.
        
        These File records will not be persisted in the database until the itemis saved or saveFiles() is invoked.
        
        :param File $file: 
        :returns: void

    .. php:method:: getResourceId()
    
        Required by Zend_Acl_Resource_Interface.
        
        Identifies Item records as relating to the Items ACL resource.
        
        :returns: string