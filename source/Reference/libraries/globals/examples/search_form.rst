Submit all of the options as an array. 

Use the ``show_advanced`` boolean to show the advanced search:

.. code-block:: php

  <?php echo search_form(array('show_advanced' => true)); ?>
  
Use the ``submit_value`` string to change the text value of the submit button:

.. code-block:: php
  
  <?php echo search_form(array('show_advanced' => true, 'submit_value' => 'I Feel Lucky')); ?>


Use the ``form_attributes`` array to add html attributes and ARIA roles to the ``form`` element:

.. code-block:: php

  <?php echo search_form(array('form_attributes' => array('role' => 'search', 'class' => 'form'))); ?>
