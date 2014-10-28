Use to add arbitrary javascript code to a page. Combine with head_js() to add to the page head inside ``<script></script>`` tags.

.. code-block:: php

    <?php queue_js_string("
          window.addEventListener('load', function() {
              FastClick.attach(document.body);
          }, false);
    "); ?>

    <?php head_js(); ?>