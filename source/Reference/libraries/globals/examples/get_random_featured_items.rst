To display a given number of featured items on a page, use this function and pass in the number of items desired:

.. code-block:: php

    <div id="featured-item">
        <h2><?php echo __('Featured Item'); ?></h2>
        <?php echo random_featured_items(2); ?>
    </div>