Use with ``head_js`` to include the links to the javascript files in the page head.

Load one javascript file from the default 'javascripts' folder within the theme directory:

.. code-block:: php

    <?php queue_js_file('my_js_file'); ?>

    <?php head_js(); ?>

Load two javascript files from the default 'javascripts' folder:

.. code-block:: php

    <?php queue_js_file(array('my_js_file', 'another_js_file')); ?>

    <?php head_js(); ?>

Load one javascript file from the default 'javascripts' folder with a conditional statement:

.. code-block:: php

    <?php queue_js_file('my_js_file', 'javascripts', array('conditional' => '(gte IE 6)&(lte IE 8)')); ?>

    <?php head_js(); ?>