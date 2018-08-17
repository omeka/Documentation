.. _adminhead:

##########
admin_head
##########

*****
Usage
*****

Adds content to the header of the admin theme.

This hook is fired by the ``header.php`` script, which is loaded by a call to ``head()`` while it is populating the ``<head>`` tag for the admin theme. 

Functions attaching to this hook can directly output HTML into the ``<head>``, or use functions like :php:func:`queue_css_file` and :php:func:`queue_js_file`.

Plugins will likely not need to add content to the admin-side ``<head>`` for every page, but the passed request object can be used to include content on particular pages only. 


*********
Arguments
*********

:php:class:`Omeka_View` view
    The view object



********
Examples
********

********
See Also
********

* :php:func:`queue_css_file`
* :php:func:`queue_css_string`
* :php:func:`queue_css_url`
* :php:func:`queue_js_file`
* :php:func:`queue_js_string`
* :php:func:`queue_js_url`
