##############
release_object
##############

*******
Summary
*******

.. include:: summary/release_object.rst

.. php:function:: release_object($var)

    Release an object from memory.
    
    Use this fuction after you are done using an Omeka model object to prevent memory leaks.  Required because PHP 5.2
    does not do garbage collection on circular references.
    
    :param unknown $var:

*****
Usage
*****

.. include:: usage/release_object.rst

********
Examples
********

.. include:: examples/release_object.rst

********
See Also
********

.. include:: see_also/release_object.rst

