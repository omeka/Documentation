###################
body_tag_attributes
###################

*****
Usage
*****

Filters the tags applied to the ``<body>`` element of the page

*****
Value
*****

``array`` $attributes

    Attributes to add to or alter


*********
Arguments
*********

None


********
Examples
********


.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = array('body_tag_attributes');
    
        public function filterBodyTagAttributes($attributes)
        {
            //add a class when users are logged in
            
            if(current_user()) {
                $attributes['class'] = trim("logged-in " . $attributes['class']);
                
            }
            return $attributes;        
        }
    }
    
    