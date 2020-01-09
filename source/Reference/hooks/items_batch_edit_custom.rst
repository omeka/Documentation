#######################
items_batch_edit_custom
#######################

*****
Usage
*****

Handles custom content added to the batch edit form by plugins using the
:doc:`admin_items_batch_edit_form` hook.

The hook fires once for each item being edited.

Note: changes made in this hook are not automaticaly saved, so you must call
``save()`` on the item yourself, or use a function like :php:func:`update_item`
that also saves.

*********
Arguments
*********

:php:class:`Item` item
    The Item currently being edited.

*mixed* custom
    The "custom" data from the batch edit form.
        
********
Examples
********
    
    
********
See Also
********

:doc:`admin_items_batch_edit_form`    
