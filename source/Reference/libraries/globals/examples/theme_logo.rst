Use to display a logo image, which is set in the theme options. Combine with ``link_to_home_page()`` to wrap the image tag with a link to the home page:

.. code-block:: php

    <div id="site-title">
        <?php echo link_to_home_page(theme_logo()); ?>
    </div>