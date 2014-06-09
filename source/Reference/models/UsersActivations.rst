----------------
UsersActivations
----------------

.. php:class:: UsersActivations

    Package: :doc:`Record </Reference/packages/Record/index>`

    An activation code for a User.

    .. php:attr:: user_id
    
        The ID of the User this activation code is for.

    .. php:attr:: url
    
        Random activation key.

    .. php:attr:: added
    
        Date this activation key was created.

    .. php:attr:: _related
    
        Related records.

    .. php:method:: factory(User $user)
    
        Get a new UsersActivations for a User.
        
        :param User $user: 
        :returns: UsersActivations

    .. php:method:: beforeSave($args)
    
        Before-save hook.
        
        Set the timestamp and create a random key.
        
        :param unknown $args:

    .. php:method:: getUser()
    
        Get the User for this Activation.
        
        :returns: User