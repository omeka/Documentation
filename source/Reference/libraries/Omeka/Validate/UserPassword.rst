---------------------------
Omeka_Validate_UserPassword
---------------------------

.. php:class:: Omeka_Validate_UserPassword

    Validate a password to see if it matches that of an existing user.

    .. php:const:: INVALID
    
    
    
        Invalid password error.

    .. php:attr:: _messageTemplates
    
        Error message templates.

    .. php:attr:: _user
    
        User to check the password against.

    .. php:method:: __construct(User $user)
    
        :param User $user:

    .. php:method:: isValid(string $value, null $context)
    
        Validate against a user's stored password.
        
        :param string $value: Password to check.
        :param null $context: Not used.