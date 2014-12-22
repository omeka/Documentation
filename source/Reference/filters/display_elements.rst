
################
display_elements
################

*****
Usage
*****

Filters the element sets and elements displayed by the :php:func:`all_element_texts` function.

*****
Value
*****

``array`` $elementSets
    All the elements, keyed by element set.

*********
Arguments
*********

None

********
Examples
********

Prevent display of the Dublin Core Title and Description elements:

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('display_elements');
        
        public function filterDisplayElements($elementSets)
        {
            foreach($elementSets as $set => $elements) {
                if ($set == 'Dublin Core') {
                    foreach ($elements as $key => $element) {
                        if ($element->name == 'Title' || $element->name == 'Description') {
                            unset($elementSets['Dublin Core'][$key]);
                        }
                    }
                } 
            }
            return $elementSets;
        }    
    }


