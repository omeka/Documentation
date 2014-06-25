.. _fpaginationlinks:

#############################################################################
``pagination_links`` — Get HTML for a pagination control for a browse page.
#############################################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/pagination_links.rst

.. php:function:: pagination_links($options = array())

    Get HTML for a pagination control for a browse page.
    
    :type $options: array
    :param $options: Configurable parameters for the pagination links. The following options are available: - 'scrolling_style' (string) See Zend_View_Helper_PaginationControl for more details.  Default 'Sliding'. - 'partial_file' (string) View script to use to render the pagination HTML. Default is 'common/pagination_control.php'. - 'page_range' (integer) See Zend_Paginator::setPageRange() for details. Default is 5. - 'total_results' (integer) Total results to paginate through. Default is provided by the 'total_results' key of the 'pagination' array that is typically registered by the controller. - 'page' (integer) Current page of the result set.  Default is the 'page' key of the 'pagination' array. - 'per_page' (integer) Number of results to display per page. Default is the 'per_page' key of the 'pagination' array.
    :returns: string HTML for the pagination links.

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/pagination_links.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/pagination_links.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/pagination_links.rst

