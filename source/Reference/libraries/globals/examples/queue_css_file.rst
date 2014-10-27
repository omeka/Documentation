Identify the CSS files located in the 'css' folder in your theme directory. CSS files queued here will be printed to the header with the ``head_css()`` function :

.. code-block:: php

    <?php 
        queue_css_file('style');
        head_css();
    ?>

Load multiple CSS files using an array:

.. code-block:: php

    <?php 
        queue_css_file(array('style', 'screen'));
        head_css();
    ?>

Load a CSS file from a folder within the default 'css folder' and add a conditional statement:

.. code-block:: php

    <?php
        queue_css_file('media/960min', 'only screen and (min-width: 960px)');
        head_css();
    ?>

