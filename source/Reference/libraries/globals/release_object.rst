.. _freleaseobject:

#####################################################
``release_object`` — Release an object from memory.
#####################################################

:doc:`Utility-related functions </Reference/packages/Function/Utility/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/release_object.rst

.. php:function:: release_object($var)

    Release an object from memory.
    
    Use this fuction after you are done using an Omeka model object to prevent
    memory leaks.  Required because PHP 5.2 does not do garbage collection on
    circular references.
    
    :param $var:

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

