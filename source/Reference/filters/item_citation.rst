#############
item_citation
#############

*****
Usage
*****

Filters or replaces the default citation displayed for an item.

*****
Value
*****

``string`` $citation

    The citation created by Omeka

*********
Arguments
*********

:php:class:`Item` item

    The item for the citation

********
Examples
********

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
        protected $_filters = array('item_citation');
        
        public filterItemCitation($citation, $args)
        {
            $citation = "";
            return $citation;
        }    
    }


********
See Also
********

:php:func:`item_citation`


