
Load one javascript file from the default 'javascripts' folder within the theme directory:

.. code-block:: php

    <?php queue_js_file('my_js_file'); ?>

Load two javascript files from the default 'javascripts' folder:

.. code-block:: php

    <?php queue_js_file(array('my_js_file', 'another_js_file')); ?>

Load one javascript file from the default 'javascripts' folder with a conditional statement:

.. code-block:: php

    <?php queue_js_file('my_js_file', 'javascripts', array('conditional' => '(gte IE 6)&(lte IE 8)')); ?>

