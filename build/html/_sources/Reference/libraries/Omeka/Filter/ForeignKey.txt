-----------------------
Omeka_Filter_ForeignKey
-----------------------

.. php:class:: Omeka_Filter_ForeignKey

    Converts input into values suitable for use as Omeka 'id' key values.

    .. php:method:: filter(mixed $value)
    
        Convert any value into an unsigned integer that would be valid
        if stored as a foreign key in a database table.
        
        This will return null for any value that falls outside the rangeof an unsigned integer (string, negative numbers,
        etc.)
        
        :param mixed $value: Input value.
        :returns: integer