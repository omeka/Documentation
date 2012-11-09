##########
users_form
##########

*****
Usage
*****

Adds content to the user form.

.. note::

    If you are looking up any information about the user, wrap the operations in an if statement like so:

    .. code-block:: php
        
        if($user->id) {
            //your operations and output
        }

    This is necessary because the admin view of users includes a form to add a user, which includes a new User object. Because it is new, it does not yet exist in the database. The result is that if your plugin tries to do any operations on it, it throws a database error. Checking for $user->id ensures that the user exists in the database first. 

*********
Arguments
*********

:php:class:`User` user
    The user object

:php:class:`Omeka_Form` form
    The form to modify

********
Examples
********


