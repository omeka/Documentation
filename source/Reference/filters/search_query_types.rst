.. _search_query_types:

##################
search_query_types
##################

*****
Usage
*****

Add a new search query type for the advanced search form

*****
Value
*****

``array`` $searchQueryTypes
    Array of query types

*********
Arguments
*********

None

********
Examples
********

The original array is

.. code-block:: php

    $searchQueryTypes = array(
        'keyword'     => __('Keyword'), 
        'boolean'     => __('Boolean'), 
        'exact_match' => __('Exact match'), 
    );

To implement an 'ends with' search query type, you must use both this filter, and the :doc:`../hooks/search_sql` hook

.. code-block:: php
    
    class EndsWithPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('search_query_types');
        
        protected $_hooks = array('search_sql');
        
        public function filterSearchQueryTypes($queryTypes)
        {
            // Register the name of your custom query type. The key should be the
            // type's GET query value; the values should be the human readable and
            // internationalized version of the query type.
            $queryTypes['ends_with'] = __('Ends with');
            return $queryTypes;        
        }
        
        public function hookSearchSql($args)
        {
            $params = $args['params'];
            if ('ends_with' == $params['query_type']) {
                $select = $args['select'];
                // Make sure to reset the existing WHERE clause.
                $select->reset(Zend_Db_Select::WHERE);
                $select->where('`text` REGEXP ?', $params['query'] . '[[:>:]]');
            }        
        
        }    
    }


********
See Also
********

:php:func:`get_search_query_types`

:ref:`modelbrowsesql`

