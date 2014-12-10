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


Include the ``wrapperTags`` array when creating a sortable table, as in the admin view. Note that the column with the "Type" label is not sortable because no property name has been entered.

.. code-block:: php
  :emphasize-lines: 4

  <?php
  $browseHeadings[__('Title')] = 'Dublin Core,Title';
  $browseHeadings[__('Creator')] = 'Dublin Core,Creator';
  $browseHeadings[__('Type')] = null;
  $browseHeadings[__('Date Added')] = 'added';

  echo browse_sort_links($browseHeadings, array('link_tag' => 'th scope="col"', 'list_tag' => ''));
  ?>
