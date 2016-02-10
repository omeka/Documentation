##################
before_save_record
##################

*****
Usage
*****

Fires before any database record is saved. This includes both insert and update operations. 

Since this hook fires before the record is saved, the record ID will not be available, but changes made to any other record properties will be saved.

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


