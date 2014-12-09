Use the ``show_empty_elements`` option to override the site configurations, either always showing or always hiding the empty elements.

.. code-block:: php

  <?php echo all_element_texts('item', array('show_empty_elements' => true));?>


Use the ``show_empty_elements`` option to set the text for the empty elements. The text will only display if the "Show Empty Elements" is enabled in the site configurations.

.. code-block:: php

  <?php echo all_element_texts('item', array('show_empty_elements' => 'This data is not available.'));?>


Use the ``show_element_set_headings`` option to override the site configurations, either always showing or always hiding the names of the different element sets.

.. code-block:: php

  <?php echo all_element_texts('item', array('show_element_set_headings' => true));?>


Use the ``show_element_sets`` option to dictate which element sets to display. Available sets include 'Item Type Elements' and those listed at ``'[your_Omeka_url]/admin/element-sets'``

.. code-block:: php

  <?php echo all_element_texts('item', array('show_element_sets' => array('Dublin Core', 'Item Type Elements'))); ?>
