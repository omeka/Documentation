items_search_form() can be used to include a search form on a page. Use the $props array to set the id or class information for the form element.

.. code-block:: php

   <?php echo items_search_form(array('id' => "items-form")); ?>


Use the $buttonText parameter to modify the submit button text.

.. code-block:: php

  <?php echo items_search_form(array(), current_url(), "I'm Feeling Lucky"); ?>
