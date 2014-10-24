Load one javascript file from the default 'javascripts' folder:

.. code-block:: php

    <?php queue_js_file('my-js-file'); ?>

Load two javascript files from the default 'javascripts' folder:

.. code-block:: php

    <?php queue_js_file(array('my-js-file', 'my-other-js-file')); ?>

Load one javascript file from the default 'javascripts' folder with a conditional statement:

.. code-block:: php

    <?php queue_js_file('my-js-file', 'javascripts', array('conditional' => '(gte IE 6)&(lte IE 8)')); ?>