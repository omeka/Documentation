Get the image associated with an individual record, such as a collection or an exhibit. Use the ``$imageType`` string to set the image size.

.. code-block:: php

    <?php if ($collectionImage = record_image('collection', 'square_thumbnail')): ?>
        <?php echo link_to_collection($collectionImage, array('class' => 'image')); ?>
    <?php endif; ?>
