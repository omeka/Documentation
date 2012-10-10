################
pagination_links
################

*******
Summary
*******

.. include:: summary/pagination_links.rst

.. php:function:: pagination_links(array $options = Array)

    Return HTML for the set of pagination links.
    
    :param array $options: Configurable parameters for the pagination links. The following options are available:         
    
        .. raw:: html
    
           <ul>
               <li>'scrolling_style' (string) See Zend_View_Helper_PaginationControl for 
             more details.  Default 'Sliding'.</li>
               <li>'partial_file' (string) View script to use to render the pagination 
             HTML. Default is 'common/pagination_control.php'.</li>
               <li>'page_range' (integer) See Zend_Paginator::setPageRange() for details.
             Default is 5.</li>
               <li>'total_results' (integer) Total results to paginate through. Default is
             provided by the 'total_results' key of the 'pagination' array that is 
             typically registered by the controller.</li>
               <li>'page' (integer) Current page of the result set.  Default is the 'page'
             key of the 'pagination' array.</li>
               <li>'per_page' (integer) Number of results to display per page. Default is
             the 'per_page' key of the 'pagination' array.</li>
             
    
        .. raw:: html
    
           <ul>

*****
Usage
*****

.. include:: usage/pagination_links.rst

********
Examples
********

.. include:: examples/pagination_links.rst

********
See Also
********

.. include:: see_also/pagination_links.rst

