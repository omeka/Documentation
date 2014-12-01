Add a link to a print.css file located in the 'css' directory:

.. code-block:: php

    <head>
        <link href="<?php echo css_src('print'); ?>" media="all" rel="stylesheet" type="text/css" />
    </head>