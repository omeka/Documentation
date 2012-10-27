-----------
Mixin_Owner
-----------

.. php:class:: Mixin_Owner

    Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

    Mixin for models that have a user that is their "owner."

    .. php:attr:: _record
    


    .. php:attr:: _column
    


    .. php:method:: __construct($record, $column = owner_id)
    
        :param unknown $record: 
        :param unknown $column:

    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: setOwner(User $user)
    
        Set the record's owner.
        
        :param User $user:

    .. php:method:: getOwner()
    
        Get the record's owner.
        
        If the record has no user, this method returns null.
        
        :returns: User|null

    .. php:method:: isOwnedBy(User $user)
    
        Check if the given User owns this record.
        
        :param User $user: 
        :returns: boolean