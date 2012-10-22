-----------------
Omeka_Filter_Time
-----------------

.. php:class:: Omeka_Filter_Time

    Package: :doc:`/Reference/packages/Filter/index`

    Converts to and from MySQL time representations.

    .. php:method:: filter(string $hour, string $minute, string $second)
    
        Convert a hour, minute and second into a valid MySQL time.
        If the resulting time would be 00:00:00, return null instead.
        
        :param string $hour: 
        :param string $minute: 
        :param string $second: 
        :returns: string|null

    .. php:method:: split(string $time)
    
        Split a valid MySQL time.
        
        :param string $time: 
        :returns: array Contains the following keys: 'hour', 'minute', 'second'.