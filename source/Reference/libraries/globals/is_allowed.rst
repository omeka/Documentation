##########
is_allowed
##########

:doc:`User-related functions </Reference/packages/Function/User/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/is_allowed.rst

.. php:function:: is_allowed($resource, $privilege)

    Check the ACL to determine whether the current user has proper permissions.
    
    .. code-block:: php 
    
    
    	                   is_allowed('Items', 'showNotPublic');
    Will check if the user has permission to view Items that are not public.
    
    :param unknown $resource: 
    :param unknown $privilege:

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/is_allowed.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/is_allowed.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/is_allowed.rst

