``get_records()`` retrieves different kind of records from the database. You can use it when other record queries don't work for you.

.. code-block:: php

    $items = get_records('Item',array('tags'=>$itemTags, 'range'=>$itemIds, 'collection'=>$itemCollection, 'type'=>$itemType),50);
    
This example uses four different parameters in the ``$params`` array to narrow down the range of **items** selected:

- ``tags`` uses a string of tag names to lookup items by tag
- ``range`` allows you to select records by ID ranges. For example: ``1-5,8,15``
- ``collection`` allows you to select a given collection ID.
- ``type`` allows you to select a given item type by ID. 

.. code-block:: php
    
    $exhibits = get_records('Exhibit', array('slug'=>$exhibitSlugs, 'tags'=>$exhibitTags), 50);

This example uses two different parameters in the ``$params`` array to narrow down the range of **exhibits** selected:

- ``slug`` allows you to select exhibits by comma-separated slugs
- ``tags`` uses a string of tag names to lookup exhibits by tag

In both cases, you can then iterate through the array of records that is returned in order to display them or perform further processing.
