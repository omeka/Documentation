Use together with ``head_css`` to load css styles into the page head within ``<style></style>`` tags:

.. code-block:: php

    <?php queue_css_string("input.add-element {display: block}"); ?>

    <?php head_css(); ?>
    