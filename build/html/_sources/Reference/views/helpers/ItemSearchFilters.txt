-----------------------------------
Omeka_View_Helper_ItemSearchFilters
-----------------------------------

.. php:class:: Omeka_View_Helper_ItemSearchFilters

    Package: :doc:`/Reference/packages/View\Helper/index`

    Show the currently-active filters for a search/browse.

    .. php:method:: itemSearchFilters(array $params)
    
        Get a list of the currently-active filters for item browse/search.
        
        :param array $params: Optional array of key-value pairs to use instead of reading the current params from the request.
        :returns: string HTML output