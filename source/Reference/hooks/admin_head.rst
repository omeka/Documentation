.. _adminhead:

##########
admin_head
##########

*****
Usage
*****

Adds content to the header of the admin theme.

This hook is fired by the ``header.php`` script, which is loaded by a call to ``head()`` while it is populating the ``<head>`` tag for the admin theme. 

Functions attaching to this hook can directly output HTML into the ``<head>``, or use functions like :php:func:`queue_css` and :php:func:`queue_js`.

Plugins will likely not need to add content to the admin-side ``<head>`` for every page, but the passed request object can be used to include content on particular pages only. 


*********
Arguments
*********

:php:class:`Omeka_View` view
    The view object



********
Examples
********


