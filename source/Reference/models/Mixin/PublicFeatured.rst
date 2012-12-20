--------------------
Mixin_PublicFeatured
--------------------

.. php:class:: Mixin_PublicFeatured

    Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

    Adds default behavior associated with the 'public' and 'featured' flags.

    .. php:attr:: _wasPublic
    


    .. php:attr:: _wasFeatured
    


    .. php:method:: __construct(Omeka_Record_AbstractRecord $record)
    
        Constructor
        
        :param Omeka_Record_AbstractRecord $record: The underlying record

    .. php:method:: isPublic()
    
        Returns whether the record is public or not.
        
        :returns: boolean

    .. php:method:: setPublic(boolean $flag)
    
        Sets whether the record is public or not.
        
        :param boolean $flag: Whether the record is public or not

    .. php:method:: isFeatured()
    
        Returns whether the record is featured or not.
        
        :returns: boolean

    .. php:method:: setFeatured(boolean $flag)
    
        Sets whether the record is featured or not.
        
        :param boolean $flag: Whether the record is featured or not

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: afterSave($args)
    
        :param unknown $args:

    .. php:method:: _fireHook(string $state, boolean $flag)
    
        Fires a hooks like 'make_item_public', 'make_collection_not_featured', etc.
        
        :param string $state: Currently, 'public' or 'featured'
        :param boolean $flag:

    .. php:method:: _getHookName(string $state, boolean $flag)
    
        Retrieve formatted hooks like 'make_item_public', 'make_collection_not_featured', etc.
        
        :param string $state: Currently, 'public' or 'featured'
        :param boolean $flag: 
        :returns: string The hook name