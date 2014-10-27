Use to load in external stylesheets, such as Google Fonts. Add link to page head using ``head_css()``:

.. code-block:: php

    <?php
      queue_css_url('http://fonts.googleapis.com/css?family=Raleway:400,600');
      head_css();
    ?>