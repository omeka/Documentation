-----------------------
Omeka_Filter_ForeignKey
-----------------------

Package: :doc:`Filter </Reference/packages/Filter/index>`

.. php:class:: Omeka_Filter_ForeignKey

implements :php:interface:`Zend_Filter_Interface`

    Converts input into values suitable for use as Omeka 'id' key values.

    .. php:method:: filter($value)

        Convert any value into an unsigned integer that would be valid
        if stored as a foreign key in a database table.

        This will return null for any value that falls outside the range of an
        unsigned integer (string, negative numbers, etc.)

        :type $value: mixed
        :param $value: Input value.
        :returns: int
