Use the ``links`` array to set the properties on which items can be sorted in the browse views. The labels are arbitrary, while the property names are determined by the element set or the record model.

.. code-block:: php

  <?php
    $sortLinks[__('Title')] = 'Dublin Core,Title';
    $sortLinks[__('Creator')] = 'Dublin Core,Creator';
    $sortLinks[__('Date Added')] = 'added';
  ?>
  <div id="sort-links">
      <span class="sort-label"><?php echo __('Sort by: '); ?></span><?php echo browse_sort_links($sortLinks); ?>
  </div>
