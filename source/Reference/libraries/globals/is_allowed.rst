.. _fisallowed:

########################################################################
``is_allowed`` — Check whether the current user has a give permission.
########################################################################

:doc:`User-related functions </Reference/packages/Function/User/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/is_allowed.rst

.. php:function:: is_allowed($resource, $privilege)

    Check whether the current user has a give permission.
    
    :type $resource: string|Zend_Acl_Resource_Interface
    :param $resource: The name of a resource, or a record implementing Zend_Acl_Resource_Interface
    :type $privilege: string|null
    :param $privilege: The privilege to check for the resource.
    :returns: bool

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

