---
Tag
---

.. php:class:: Tag

    .. php:attr:: name
    


    .. php:method:: __toString()

    .. php:method:: _delete()
    
        Must also delete the taggings associated with this tag
        
        :returns: void

    .. php:method:: _validate()

    .. php:method:: fieldIsUnique($field, $value)
    
        The check for unique tag names must take into account CASE SENSITIVITY, 
        which is accomplished via COLLATE utf8_bin sql
        
        :param unknown $field: 
        :param unknown $value: 
        :returns: bool

    .. php:method:: rename(array $new_names)
    
        Rename a tag.
        
        Any records tagged with the "old" tag will be tagged with each of the tags given in $new_names. The original tag
        will be deleted (unless it is given as one of the $new_names).
        
        :param array $new_names: Names of the tags this one should be renamed to.
        :returns: void