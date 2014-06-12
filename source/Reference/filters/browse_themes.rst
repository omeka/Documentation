#############
browse_themes
#############

*****
Usage
*****

Allows you to filter the list of themes on the admin themes browse page

*****
Value
*****

``array`` $themes
    Array of themes keyed by their directory name.



*********
Arguments
*********

None


********
Examples
********

Ignore themes without images

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
    
        protected $_filters = array('browse_themes');
        
        public filterBrowseThemes($themes)
        {
            foreach($themes as $key=>$theme) {
                if(empty($theme->image)) {
                    unset($themes['key'];
                }
            }
            
            return $themes;
        }    
    }

