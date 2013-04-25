#######################
items_batch_edit_custom
#######################

*****
Usage
*****

Handles custom content added to the batch edit form by plugins using the
:doc:`admin_items_batch_edit_form` hook.

The hook fires once for each item being edited.

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
