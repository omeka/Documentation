:php:func:`head_js` actually outputs the scripts. All themes should already call ``head_js`` themselves,
so you can just use the queue functions.

If writing a theme, ``queue_js_*`` functions must be called before the call to ``head_js``. If writing a plugin,
you make these calls within the  :doc:`/Reference/hooks/admin_head` or :doc:`/Reference/hooks/public_head` hooks.

The ``$options`` array is passed as the ``$attrs`` parameter to the
Zend Framework `headScript <http://framework.zend.com/manual/1.12/en/zend.view.helpers.html#zend.view.helpers.initial.headscript>`_
helper. This can be used to set some attributes on the ``<script>`` tag as
well as to enable some specific functionality of the ZF helper like IE
conditional comments.
