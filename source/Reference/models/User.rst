----
User
----

.. php:class:: User

    Package: :doc:`Record </Reference/packages/Record/index>`

    A user and its metadata.

    .. php:const:: USERNAME_MIN_LENGTH
    
    
    
        Minimum username length.

    .. php:const:: USERNAME_MAX_LENGTH
    
    
    
        Maximum username length.

    .. php:const:: PASSWORD_MIN_LENGTH
    
    
    
        Minimum password length.

    .. php:const:: INVALID_EMAIL_ERROR_MSG
    
    
    
        Error message for an invalid email address.

    .. php:const:: CLAIMED_EMAIL_ERROR_MSG
    
    
    
        Error message for an already-taken email address.

    .. php:attr:: username
    
        This User's username.

    .. php:attr:: password
    
        The hashed password.
        
        This field should never contain the plain-text password.  Alwaysuse setPassword() to change the user password.

    .. php:attr:: salt
    
        The salt for the hashed password.

    .. php:attr:: active
    
        Whether this user is active and can log in.

    .. php:attr:: role
    
        This user's role.

    .. php:attr:: name
    
        This user's full or display name.

    .. php:attr:: email
    
        This user's email address.

    .. php:method:: beforeSave($args)
    
        Before-save hook.
        
        Check the current user's privileges to change user roles before saving.
        
        :param unknown $args:

    .. php:method:: filterPostData(array $post)
    
        Filter form POST input.
        
        Transform usernames to lowercase alphanumeric.
        
        :param array $post: 
        :returns: array Cleaned POST data.

    .. php:method:: setPostData($post)
    
        Set data from POST to the record.
        
        Removes the 'password' and 'salt' entries, if passed.
        
        :param unknown $post:

    .. php:method:: _validate()
    
        Validate this User.

    .. php:method:: upgradeHashedPassword(string $username, string $password)
    
        Upgrade the hashed password.
        
        Does nothing if the user/password isincorrect, or if same has been upgraded already.
        
        :param string $username: 
        :param string $password: 
        :returns: boolean False if incorrect username/password given, otherwise true when password can be or has been upgraded.

    .. php:method:: getRoleId()
    
        Get this User's role.
        
        Required by Zend_Acl_Role_Interface.
        
        :returns: string

    .. php:method:: getResourceId()
    
        Get the Resource ID for the User model.
        
        Required by Zend_Acl_Resource_Interface.
        
        :returns: string

    .. php:method:: generateSalt()
    
        Generate a simple 16 character salt for the user.

    .. php:method:: setPassword(string $password)
    
        Set a new password for the user.
        
        Always use this method to set a password, do not directly set thepassword or salt properties.
        
        :param string $password: Plain-text password.

    .. php:method:: hashPassword(string $password)
    
        SHA-1 hash the given password with the current salt.
        
        :param string $password: Plain-text password.
        :returns: string Salted and hashed password.