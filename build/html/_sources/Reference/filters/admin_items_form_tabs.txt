#####################
admin_items_form_tabs
#####################

*****
Usage
*****


*********
Arguments
*********

``array`` tabs
    An array of the item form tabs. The keys are the tab names, and the values are the HTML content of each tab. A filter function should modify this array and return it.  

:php:class:`Item` item
    The Item being edited. Filter functions can use this parameter to change the tabs or content on an item-by-item basis. 

********
Examples
********


