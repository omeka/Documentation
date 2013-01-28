#################
after_save_record
#################

*****
Usage
*****

Fires after any database record is saved. This includes both insert and update operations.

Since this hook fires after the record is saved, the record ID will be available, but changes made to any other record properties will not be saved. 

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


