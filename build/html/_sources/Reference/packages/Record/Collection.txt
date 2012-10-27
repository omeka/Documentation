----------
Collection
----------

.. php:class:: Collection

    Package: :doc:`Record </Reference/packages/Record/index>`

    A collection and its metadata.

    .. php:attr:: public
    


    .. php:attr:: featured
    


    .. php:attr:: added
    


    .. php:attr:: modified
    


    .. php:attr:: owner_id
    


    .. php:attr:: _related
    


    .. php:method:: getProperty(string $property)
    
        Get a property about this collection.
        
        :param string $property: The property to get, always lowercase.
        :returns: mixed The value of the property

    .. php:method:: totalItems()
    
        Determine the total number of items associated with this collection.
        
        :returns: integer

    .. php:method:: setAddedBy(User $user)
    
        Set the user who added the collection.
        
        Note that this is not to be confused with the collection's "contributors".
        
        :param User $user:

    .. php:method:: getResourceId()
    
        Required by Zend_Acl_Resource_Interface.
        
        Identifies Collection records as relating to the Collections ACLresource.
        
        :returns: string

    .. php:method:: hasContributor()
    
        Returns whether or not the collection has at least 1 contributor element text
        
        :returns: boolean

    .. php:method:: _initializeMixins()
    
        Initialize the mixins

    .. php:method:: filterPostData(array $post)
    
        Filter the POST data from the form.
        
        Converts public/featured flags to booleans.
        
        :param array $post: 
        :returns: array

    .. php:method:: _delete()
    
        All of the custom code for deleting an collection.
        
        :returns: void

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: afterSave()