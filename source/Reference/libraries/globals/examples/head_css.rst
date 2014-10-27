Use after ``queue_css_file()``, ``queue_css_url()``, and/or ``queue_css_string()`` to add the links to the css files and/or the css declarations to the page head:

.. code-block:: php

    <?php 
        queue_css_file('style');
        head_css();
    ?>