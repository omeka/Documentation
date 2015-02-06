Add a tag cloud to a page. Use the ``$link`` parameter to set the base url for the tags.

.. code-block:: php

  <?php echo tag_cloud($tags, 'exhibits/browse'); ?>

Use the ``$maxClasses`` parameter to set the max count used to calculate tag size. Range supported by themes is 1-9.

.. code-block:: php

  <?php echo tag_cloud($tags, 'exhibits/browse', 5); ?>

Use the ``$tagNumber`` and ``$tagNumberOrder`` parameters to display the count for each tag. The possible values for ``$tagNumberOrder`` are 'before' and 'after'.

.. code-block:: php

  <?php echo tag_cloud($tags, 'exhibits/browse', 5, true, 'before'); ?>
