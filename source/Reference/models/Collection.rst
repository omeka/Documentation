----------
Collection
----------

.. php:class:: Collection

    Package: :doc:`Record </Reference/packages/Record/index>`

    A collection and its metadata.

    .. php:attr:: public
    
        Whether or not the collection is publicly accessible.

    .. php:attr:: featured
    
        Whether or not the collection is featured.

    .. php:attr:: added
    
        Date the collection was added.

    .. php:attr:: modified
    
        Date the collection was last modified.

    .. php:attr:: owner_id
    
        ID for the User that created this collection.

    .. php:attr:: _related
    
        Related records.

    .. php:method:: _initializeMixins()
    
        Initialize the mixins.

    .. php:method:: getProperty(string $property)
    
        Get a property about this collection.
        
        Valid properties for a Collection include:* (int) public* (int) featured* (string) added* (string) modified* (int) owner_id* (int) total_items
        
        :param string $property: The property to get, always lowercase.
        :returns: mixed The value of the property

    .. php:method:: totalItems()
    
        Get the total number of items in this collection.
        
        :returns: int

    .. php:method:: setAddedBy(User $user)
    
        Set the user who added the collection.
        
        Note that this is not to be confused with the collection's "contributors".
        
        :param User $user:

    .. php:method:: getResourceId()
    
        Required by Zend_Acl_Resource_Interface.
        
        Identifies Collection records as relating to the Collections ACLresource.
        
        :returns: string

    .. php:method:: hasContributor()
    
        Return whether the collection has at least 1 contributor element text.
        
        :returns: bool

    .. php:method:: filterPostData(array $post)
    
        Filter the POST data from the form.
        
        Converts public/featured flags to booleans.
        
        :param array $post: 
        :returns: array

    .. php:method:: _delete()
    
        All of the custom code for deleting an collection.
        
        Delete the element texts for this record.
        
        :returns: void

    .. php:method:: _dissociateItems()
    
        Set items attached to this collection back to "no collection."

    .. php:method:: beforeSave($args)
    
        Before-save hook.
        
        Fire the before-save element texts code.
        
        :param unknown $args:

    .. php:method:: afterSave()
    
        After-save hook.
        
        Handle public/private status for search.

    .. php:method:: getFile()
    
        Get a representative file for this Collection.
        
        :returns: File|null