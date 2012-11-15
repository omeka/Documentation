Generates HTML elements for sorting based on the metadata given.

When the records are presented as a table, as in most admin browse views, ``$wrapperTags`` should be:

.. code-block:: php

    array('link_tag' => 'th scope="col"', 'list_tag' => '')
    
    
Otherwise, you will want to add text and/or styling to make clear that the list presented is for sorting the displayed records.    
    
    
    