``css_src()`` is a helper function used when referencing a css file within a theme, 
and commonly included within a theme's ``header.php`` file. It returns the path to a css file 
located in the css folder of that theme, usually located in ``themes/YourTheme/css``.

.. note::

   The :php:func:`queue_css_file` helper is preferred to this one for most use cases. 