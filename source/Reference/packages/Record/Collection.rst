----------
Collection
----------

.. php:class:: Collection

    Package: :doc:`/Reference/packages/Record/index`

    A collection and its metadata.

    .. php:attr:: name
    


    .. php:attr:: description
    


    .. php:attr:: collectors
    


    .. php:attr:: public
    


    .. php:attr:: featured
    


    .. php:attr:: added
    


    .. php:attr:: modified
    


    .. php:attr:: owner_id
    


    .. php:method:: _initializeMixins()

    .. php:method:: getProperty(string $property)
    
        Get a property about this collection.
        
        :param string $property: The property to get, always lowercase.

    .. php:method:: hasCollectors()
    
        Determine whether or not the collection has collectors associated with it.
        
        :returns: boolean

    .. php:method:: totalItems()
    
        Determine the total number of items associated with this collection.
        
        :returns: integer

    .. php:method:: getCollectors()
    
        Retrieve a list of all the collectors associated with this collection.
        
        :returns: array List of strings.

    .. php:method:: filterPostData(array $post)
    
        Filter the POST data from the form.
        
        Trims the 'name' and 'description' strings, strips tags from thecollection name, and converts public/featured flags
        to booleans.
        
        :param array $post: 
        :returns: array

    .. php:method:: _validate()
    
        Validate the record.
        
        Checks the collection name to ensure that it is below 255 characters.

    .. php:method:: removeCollector($collector)
    
        Disassociate a collector with this collection.
        
        :param unknown $collector: 
        :returns: boolean Was successful or not.

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: addCollector(string $collector)
    
        Add a collector to the collection.
        
        Note that prior versions of Omeka allowed for entering collector metadataas Entity records.  This behavior has been
        deprecated and removed inOmeka >= 1.3.  Please use the new syntax, which is simply the string namefor the collector.
        
        :param string $collector: 
        :returns: void

    .. php:method:: setCollectors($collectorList)
    
        Set the list of collectors for this collection.
        
        :param unknown $collectorList:

    .. php:method:: setAddedBy(User $user)
    
        Set the user who added the collection.
        
        Note that this is not to be confused with the collection's "collectors".
        
        :param User $user:

    .. php:method:: getResourceId()
    
        Required by Zend_Acl_Resource_Interface.
        
        Identifies Collection records as relating to the Collections ACLresource.
        
        :returns: string

    .. php:method:: afterSave()