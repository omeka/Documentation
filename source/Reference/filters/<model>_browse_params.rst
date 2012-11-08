#####################
<model>_browse_params
#####################

*****
Usage
*****

Filters the parameters used when generating the browse page for records (the model)

.. note::

    <model> is the plural form

*****
Value
*****

``array`` $params

    Params passed to the browse query. May include both filtering and sorting parameters

*********
Arguments
*********

None

********
Examples
********

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('item_browse_params');
        
        public filterItemBrowseParams($params)
        {
            //always sort by title instead of order
            $params['sort_param'] = "Dublin Core,Title";
            return $params;
        }    
    }


********
See Also
********

:ref:`modelbrowsesql`
:php:meth:`Omeka_Db_Table::getSelectForFindBy`