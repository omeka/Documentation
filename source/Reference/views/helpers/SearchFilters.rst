-------------------------------
Omeka_View_Helper_SearchFilters
-------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_SearchFilters

extends :php:class:`Zend_View_Helper_Abstract`

    Return a list of search filters in the current request.

    .. php:method:: searchFilters($options = array())

        Return a list of current search filters in use.

        :type $options: array
        :param $options: Valid options are as follows: - id (string): the ID of the filter wrapping div.
        :returns: string
