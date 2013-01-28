##################
after_save_<model>
##################

*****
Usage
*****

Fires after a database record of type <model> is saved.

The id is available, but changes made to the record will not be saved.

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record
    The record being edited

``array or false`` post
   The post data, or false if none
   
``boolean`` insert
   Whether the record is being inserted

********
Examples
********


