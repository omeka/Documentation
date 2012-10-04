-------------------------------
Omeka_View_Helper_SearchFilters
-------------------------------

.. php:class:: Omeka_View_Helper_SearchFilters

    Show the currently-active filters for a search/browse.

    .. php:method:: searchFilters(array $params)
    
        Get a list of the currently-active filters.
        
        :param array $params: Optional array of key-value pairs to use instead of reading the current params from the request.
        :returns: string HTML output