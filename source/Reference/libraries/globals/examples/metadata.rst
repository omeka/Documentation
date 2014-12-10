Use the ``metadata`` function to get the Element Set metadata for a collection. The ``snippet`` option can be used to limit the information to only the first 150 characters.

.. code-block:: php

    <div class="collection record">
        <?php
            $description = metadata($collection, array('Dublin Core', 'Description'), array('snippet' => 150));
        ?>
        <?php if ($description): ?>
            <p class="collection-description"><?php echo $description; ?></p>
        <?php endif; ?>
    </div>


When calling the ``metadata`` function within a loop, pass in a string of the current record type.

.. code-block:: php

  <h1><?php echo metadata('collection', array('Dublin Core', 'Title')); ?></h1>


The ``metadata`` function also grabs the record metadata.

.. code-block:: php

  <h1><?php echo metadata('simple_pages_page', 'title'); ?></h1>
