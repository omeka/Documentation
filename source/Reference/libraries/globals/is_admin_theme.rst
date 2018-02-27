.. _fisadmintheme:

##################################################################################################
``is_admin_theme`` — Determine whether the script is being executed through the admin interface.
##################################################################################################

:doc:`View-related functions </Reference/packages/Function/View/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/is_admin_theme.rst

.. php:function:: is_admin_theme()

    Determine whether the script is being executed through the admin
    interface.
    
    Can be used to branch behavior based on whether or not the admin theme is
    being accessed, but should not be relied upon in place of using the ACL
    for controlling access to scripts.
    
    :returns: bool

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/is_admin_theme.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/is_admin_theme.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/is_admin_theme.rst

