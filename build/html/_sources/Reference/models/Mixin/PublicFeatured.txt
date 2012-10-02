--------------------
Mixin_PublicFeatured
--------------------

.. php:class:: Mixin_PublicFeatured

    Adds default behavior associated with the 'public' and 'featured' flags.

    .. php:attr:: _wasPublic
    


    .. php:attr:: _wasFeatured
    


    .. php:method:: isPublic()
    
        :returns: boolean

    .. php:method:: setPublic($flag)
    
        :param unknown $flag: 
        :returns: void

    .. php:method:: isFeatured()

    .. php:method:: setFeatured($flag)
    
        :param unknown $flag:

    .. php:method:: getHookName($state, $flag)
    
        Retrieve formatted hooks like 'make_item_public', 'make_collection_not_featured', etc.
        
        :param unknown $state: 
        :param unknown $flag: 
        :returns: string

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: afterSave($args)
    
        :param unknown $args:

