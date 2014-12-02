Pull header image information from the theme options and write it to the HTML page:

.. code-block:: php

    <?php echo theme_header_image(); ?>

which results in:

.. code-block:: html

    <div id="header-image">
        <img src="http://mysite/files/theme_uploads/4c62db4de9d04b8f494ca8c132392920.jpg" />
    </div>