.. _admintypepanelfields:

#########################
admin_<type>_panel_fields
#########################

*****
Usage
*****

Append content just below the save panel fields when editing using the :php:class:`Omeka_Form_Admin`. Often <type> will be a model type.

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord`|null record
    The record being edited, if one was passed in when the form was created. Otherwise, null

:php:class:`Omeka_View` view
    The view object


********
Examples
********


