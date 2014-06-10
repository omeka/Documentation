.. _admintypepanelbuttons:

##########################
admin_<type>_panel_buttons
##########################

*****
Usage
*****

Append content just below the save panel buttons when editing using the :php:class:`Omeka_Form_Admin`. Often <type> will be a model type.


*********
Arguments
*********

:php:class:`Omeka_View` view
    The view object
    
:php:class:`Omeka_Record_AbstractRecord`\|null record
    The record being edited, if a record was passed in when creating the form. Otherwise, null.

    
********
Examples
********


