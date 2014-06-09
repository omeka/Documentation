.. _freleaseobject:

##############
release_object
##############

:doc:`Utility-related functions </Reference/packages/Function/Utility/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/release_object.rst

.. php:function:: release_object($var)

    Release an object from memory.
    
    Use this fuction after you are done using an Omeka model object to preventmemory leaks.  Required because PHP 5.2 does not do garbage collection oncircular references.
    
    :param unknown $var:

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/release_object.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/release_object.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/release_object.rst

