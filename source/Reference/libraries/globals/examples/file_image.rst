Display a square thumbnail for an item and wrap it with ``class = "thumbnail"``

.. code-block:: php

    <div class="item-collapsed">
        <?php echo file_image('square_thumbnail', array('class' => 'thumbnail'), $file); ?>
    </div>