----
User
----

.. php:class:: User

    .. php:attr:: username
    


    .. php:attr:: password
    


    .. php:attr:: salt
    


    .. php:attr:: active
    


    .. php:attr:: role
    


    .. php:attr:: name
    


    .. php:attr:: email
    


    .. php:method:: beforeSave($args)
    
        :param unknown $args:

    .. php:method:: filterPostData($post)
    
        :param unknown $post:

    .. php:method:: setPostData($post)
    
        :param unknown $post:

    .. php:method:: _validate()

    .. php:method:: upgradeHashedPassword(string $username, string $password)
    
        Upgrade the hashed password.  Does nothing if the user/password is 
        incorrect, or if same has been upgraded already.
        
        :param string $username: 
        :param string $password: 
        :returns: boolean False if incorrect username/password given, otherwise true when password can be or has been upgraded.

    .. php:method:: getRoleId()

    .. php:method:: getResourceId()

    .. php:method:: generateSalt()
    
        Generate a simple 16 character salt for the user.

    .. php:method:: setPassword($password)
    
        :param unknown $password:

    .. php:method:: hashPassword($password)
    
        :param unknown $password: