Use ``img()`` to include a link to an image stored in ``themes/YourTheme/images``:
 
.. code-block:: php

    <?php 
        $themeScreenshot = img('fallback-theme.png');
    ?>

    <div class="screenshot">
        <img src="<?php echo $themeScreenshot; ?>" />
    </div>
