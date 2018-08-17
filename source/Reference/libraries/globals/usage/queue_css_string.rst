:php:func:`head_css` actually outputs the stylesheet markup. All themes should already call ``head_css`` themselves,
so you can just use the queue functions.

If writing a theme, ``queue_css_*`` functions must be called before the call to ``head_css``. If writing a plugin,
you make these calls within the  :doc:`/Reference/hooks/admin_head` or :doc:`/Reference/hooks/public_head` hooks.
