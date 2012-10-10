The ``js_tag()`` helper function retrieves JavaScript files located within the ``/javascripts/`` folder
 of a theme. By using ``js_tag()``, the relative path to the file is dynamically generated for each page.

.. note::

   The :php:func:`queue_js_file` helper is preferred to this one for most use cases. Normally, you should only continue to use this helper when you want to output an inline script in the body of the page. 