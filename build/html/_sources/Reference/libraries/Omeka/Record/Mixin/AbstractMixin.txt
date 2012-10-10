--------------------------------
Omeka_Record_Mixin_AbstractMixin
--------------------------------

.. php:class:: Omeka_Record_Mixin_AbstractMixin

    Represents a kind of mixin for Omeka_Record_AbstractRecord implementations.
    
    Any methods declared for an implementation of this class can be calledtransparently by an Omeka_Record_AbstractRecord object that uses one of thesemodules.
    
    For instance, the Item model does not have an addTags() method, but theTaggable class does.  Since Item declares Taggable as one of its modules,an Item instance call all of Taggable's methods, so that adding tagswould be as simple as calling $item->addTags('foo, bar');
    
    Note that this is not a true mixin because it cannot override any existingmethods on a Record object.

    .. php:attr:: _record
    
        Underlying record object.

    .. php:method:: __construct(Omeka_Record_AbstractRecord $record)
    
        Base mixin constructor.
        
        Store the underlying record for use in the mixin.
        
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: beforeSave($args)
    
        Callback automatically called by Omeka_Record_AbstractRecord.
        
        See the corresponding {@link Omeka_Record_AbstractRecord} method for definitions of call times.
        
        :param unknown $args: 
        :returns: void

    .. php:method:: afterSave($args)
    
        :param unknown $args:

    .. php:method:: beforeDelete()

    .. php:method:: afterDelete()