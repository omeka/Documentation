-----------------
Omeka_Filter_Date
-----------------

.. php:class:: Omeka_Filter_Date

    Package: :doc:`/Reference/packages/Filter/index`

    Converts to and from MySQL date representations.

    .. php:method:: filter(string $year, string $month, string $day)
    
        Convert a year, month and day into a valid MySQL date.
        
        If the resulting date would be 0000-00-00, return null instead.
        
        :param string $year: Numeric year value.
        :param string $month: Numeric month value.
        :param string $day: Numeric day value.
        :returns: string|null

    .. php:method:: split(string $date)
    
        Split a valid MySQL date
        
        :param string $date: 
        :returns: array Array of year, month and day values.