Use to add arbitrary javascript code to a page.

.. code-block:: php

    <?php queue_js_string("
          window.addEventListener('load', function() {
              FastClick.attach(document.body);
          }, false);
    "); ?>

