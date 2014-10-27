Use together with ``head_css`` to load css styles into the document header within ``<style></style>`` tags:

.. code-block:: php

    <?php
        queue_css_string("input.add-element {display: block}");
        head_css();
    ?>



    