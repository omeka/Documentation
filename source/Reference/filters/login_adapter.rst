#############
login_adapter
#############

*****
Usage
*****

The login adapter filter may be used to override the default way Omeka authenticates users, for example by checking against a different table.

*****
Value
*****

:php:class:`Omeka_Auth_Adapter_UserTable` $authAdapter

    The adapter to use for authenticating a user. You can return your own adapter if necessary for more complex authentication systems.


*********
Arguments
*********

:php:class:`Omeka_Form_Login` login_form

    The form to use for logging in. Can be replaced via the :ref:`login_form` filter.


********
Examples
********


