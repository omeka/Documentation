##############
release_object
##############

.. php:function:: release_object($var)

    Release an object from memory.
    
    Use this fuction after you are done using an Omeka model object to prevent memory leaks.  Required because PHP 5.2
    does not do garbage collection on circular references.
    
    :param unknown $var:

*****
Usage
*****



********
Examples
********



