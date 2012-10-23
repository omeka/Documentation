###################
Element Form Filter
###################

*****
Usage
*****

*****
Value
*****

``array`` $components

    The form components, like:
    
        .. code-block:: php
        
         array(
             'label' => [...], 
             'inputs' => [...], 
             'description' => [...], 
             'comment' => [...], 
             'add_input' => [...], 
         )

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record

    The model being edited.
    
:php:class:`Element` element

    The element being edited
    
``array`` options

    An array of additional options for the form

********
Examples
********


.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        $_filters = array('relabelItemTitle', array('ElementForm', 'Item', 'Dublin Core', 'Title'));
        
        public function relabelItemTitle($components, $args)
        {
            $components['label'] = "Label";
            return $components;
        }
    }    
    

