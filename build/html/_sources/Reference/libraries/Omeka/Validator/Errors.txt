----------------------
Omeka_Validator_Errors
----------------------

.. php:class:: Omeka_Validator_Errors

    This is an object wrapper for validation errors.  The primary advantage
    to having this class is that casting it to a string will convert the errors
    into a nicely formatted, human-readable string.

    .. php:attr:: _errors
    
        List of validation errors.

    .. php:method:: __construct(array|null $errors)
    
        :param array|null $errors: Initial errors to set.

    .. php:method:: offsetGet(mixed $key)
    
        Get an error from the list.
        Required by ArrayObject.
        
        :param mixed $key: Key into array.

    .. php:method:: offsetSet(mixed $key, mixed $val)
    
        Set an error into the list.
        Required by ArrayObject.
        
        :param mixed $key: Key into array.
        :param mixed $val: Value to store.

    .. php:method:: get()
    
        Get the array of errors.
        
        :returns: array

    .. php:method:: count()
    
        Get the number of errors.
        
        :returns: integer

    .. php:method:: __toString()
    
        Get a string representation of all the stored errors.
        
        :returns: string

    .. php:method:: offsetExists($index)
    
        :param unknown $index:

    .. php:method:: offsetUnset($index)
    
        :param unknown $index:

    .. php:method:: append($value)
    
        :param unknown $value:

    .. php:method:: getArrayCopy()

    .. php:method:: getFlags()

    .. php:method:: setFlags($flags)
    
        :param unknown $flags:

    .. php:method:: asort()

    .. php:method:: ksort()

    .. php:method:: uasort($cmp_function)
    
        :param unknown $cmp_function:

    .. php:method:: uksort($cmp_function)
    
        :param unknown $cmp_function:

    .. php:method:: natsort()

    .. php:method:: natcasesort()

    .. php:method:: unserialize($serialized)
    
        :param unknown $serialized:

    .. php:method:: serialize()

    .. php:method:: getIterator()

    .. php:method:: exchangeArray($array)
    
        :param unknown $array:

    .. php:method:: setIteratorClass($iteratorClass)
    
        :param unknown $iteratorClass:

    .. php:method:: getIteratorClass()