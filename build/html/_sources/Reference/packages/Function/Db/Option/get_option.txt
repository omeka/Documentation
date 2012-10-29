##########
get_option
##########

:doc:`Option-related functions </Reference/packages/Function/Db/Option/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/get_option.rst

.. php:function:: get_option($name)

    Get an option from the options table.
    
    If the returned value represents an object or array, it must be unserializedby the caller before use. For example:	               
    
    .. code-block:: php 
    
    
    	                   $object = unserialize(get_option('plugin_object'));
    
    :param unknown $name:

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/get_option.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/get_option.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/get_option.rst

