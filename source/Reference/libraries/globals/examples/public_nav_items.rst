You can use the public_nav_items function to create a custom browse navigation. 

.. code-block:: php

    <?php echo public_nav_items(array (
        array (
            'label' => __('Browse All'),
            'uri' => url('items/browse')
            ), 
        array (
            'label' => __('Search'),
            'uri' => url('search')
            ),
        array (
            'label' => __('Browse Text Items'),
            'uri' => url('items/browse?type=1')
            )
    )); ?>

You can find the item type numbers when viewing the 'item type' in the Admin interface. Changing the default array does not affect the navigation elements added by plugins.