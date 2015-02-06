Use ``output_format_list`` to control how the list of outputs is generated. Use true to output as an unordered list (``<ol>``).

.. code-block:: php

  <?php echo output_format_list(true); ?>

Use ``false`` to output as a string. While the default delimiter is a comma, this can be overwitten using the ``$delimiter`` parameter.

.. code-block:: php

  <?php echo output_format_list(false, ' | '); ?>
