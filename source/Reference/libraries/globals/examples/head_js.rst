Use after all desired javascript files, urls, and strings have been queued to add the javascript information to the page head.

.. code-block:: php
    :emphasize-lines: 11

    <?php
        queue_js_file(array('my_js_file', 'another_js_file'));
        queue_js_url('//ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js'); 
        queue_js_string("
          window.addEventListener('load', function() {
              FastClick.attach(document.body);
          }, false);
    "); 
    ?>

    <?php head_js(); ?>