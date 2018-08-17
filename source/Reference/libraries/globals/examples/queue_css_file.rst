Include the CSS file ``style.css`` located in the ``css`` folder in your theme:

.. code-block:: php

    <?php queue_css_file('style'); ?>

Load multiple CSS files using an array:

.. code-block:: php

    <?php queue_css_file(array('style', 'screen')); ?>

Load a CSS file and add a media query:

.. code-block:: php

    <?php queue_css_file('media/960min', 'only screen and (min-width: 960px)'); ?>

