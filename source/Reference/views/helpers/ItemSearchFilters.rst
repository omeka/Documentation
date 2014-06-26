-----------------------------------
Omeka_View_Helper_ItemSearchFilters
-----------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_ItemSearchFilters

extends :php:class:`Zend_View_Helper_Abstract`

    Show the currently-active filters for a search/browse.

    .. php:method:: itemSearchFilters($params = null)

        Get a list of the currently-active filters for item browse/search.

        :type $params: array
        :param $params: Optional array of key-value pairs to use instead of reading the current params from the request.
        :returns: string HTML output
