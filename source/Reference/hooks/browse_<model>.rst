##############
browse_<model>
##############

*****
Usage
*****

Fires on most models' browse pages. The <model> is the plural name of the model, e.g. 'items'.

*********
Arguments
*********

``array`` records
    Array of the subclasses of :php:class:`Omeka_Record_AbstractRecord` being browsed.    

.. note::
    For ``browse_tags``, there is an additional argument:
        
    ``mixed`` object
        The object record that the tags are applied to.
        


********
Examples
********
