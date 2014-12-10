Add a link to a print.css file located in the theme's ``css`` directory. Use when you need to load css files outside of the head.php file.

.. code-block:: php

    <head>
        <link href="<?php echo css_src('print'); ?>" media="all" rel="stylesheet" type="text/css" />
    </head>
