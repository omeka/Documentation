Use the ``show_element_sets`` option to dictate which element sets to display. Available sets include 'Item Type Elements' and those listed at ``'[your_Omeka_url]/admin/element-sets'``

.. code-block:: php

  <?php echo all_element_texts('item', array(‘show_element_sets’ => array(’Dublin Core’, ‘Item Type Elements’))); ?>
