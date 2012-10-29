-------------------------------
Omeka_View_Helper_SearchFilters
-------------------------------

.. php:class:: Omeka_View_Helper_SearchFilters

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    Return a list of search filters in the current request.

    .. php:method:: searchFilters(array $options = Array)
    
        Return a list of current search filters in use.
        
        :param array $options: Valid options are as follows: - id (string): the ID of the filter wrapping div.
        :returns: string