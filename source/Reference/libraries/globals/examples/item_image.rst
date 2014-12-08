Use to display an image file associated with an item. Use the parameters to control the image size and combine with ``link_to_item`` to wrap the image tag in an anchor tag.

.. code-block:: php

  <?php echo link_to_item(item_image('square_thumbnail', array('alt' => $itemTitle))); ?>
