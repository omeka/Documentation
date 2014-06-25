---------------------
Omeka_Validate_Errors
---------------------

Package: :doc:`Validate </Reference/packages/Validate/index>`

.. php:class:: Omeka_Validate_Errors

extends :php:class:`ArrayObject`

implements :php:interface:`Countable`
implements :php:interface:`Serializable`
implements :php:interface:`ArrayAccess`
implements :php:interface:`Traversable`
implements :php:interface:`IteratorAggregate`

    This is an object wrapper for validation errors.  The primary advantage
    to having this class is that casting it to a string will convert the errors
    into a nicely formatted, human-readable string.

    .. php:attr:: _errors

        protected array

        List of validation errors.

    .. php:method:: __construct($errors = null)

        :type $errors: array|null
        :param $errors: Initial errors to set.

    .. php:method:: offsetGet($key)

        Get an error from the list.
        Required by ArrayObject.

        :type $key: mixed
        :param $key: Key into array.

    .. php:method:: offsetSet($key, $val)

        Set an error into the list.
        Required by ArrayObject.

        :type $key: mixed
        :param $key: Key into array.
        :type $val: mixed
        :param $val: Value to store.

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

        :param $index:

    .. php:method:: offsetUnset($index)

        :param $index:

    .. php:method:: append($value)

        :param $value:

    .. php:method:: getArrayCopy()

    .. php:method:: getFlags()

    .. php:method:: setFlags($flags)

        :param $flags:

    .. php:method:: asort()

    .. php:method:: ksort()

    .. php:method:: uasort($cmp_function)

        :param $cmp_function:

    .. php:method:: uksort($cmp_function)

        :param $cmp_function:

    .. php:method:: natsort()

    .. php:method:: natcasesort()

    .. php:method:: unserialize($serialized)

        :param $serialized:

    .. php:method:: serialize()

    .. php:method:: getIterator()

    .. php:method:: exchangeArray($array)

        :param $array:

    .. php:method:: setIteratorClass($iteratorClass)

        :param $iteratorClass:

    .. php:method:: getIteratorClass()
