---
Tag
---

.. php:class:: Tag

    Package: :doc:`Record </Reference/packages/Record/index>`

    A tag and its metadata.

    .. php:attr:: name
    
        The tag text.

    .. php:method:: __toString()
    
        Use the tag text when using this record as a string.
        
        :returns: string

    .. php:method:: _delete()
    
        Delete handling for a tag.
        
        Delete the taggings associated with this tag.

    .. php:method:: _validate()
    
        Validate this tag.
        
        The tag "name" must be non-empty and unique.

    .. php:method:: fieldIsUnique($field, $value)
    
        Check whether a field is unique.
        
        The check for unique tag names must take into account CASE SENSITIVITY,which is accomplished via COLLATE utf8_bin sql
        
        :param unknown $field: 
        :param unknown $value: 
        :returns: bool

    .. php:method:: rename(array $new_names)
    
        Rename a tag.
        
        Any records tagged with the "old" tag will be tagged with eachof the tags given in $new_names. The original tag will bedeleted (unless it is given as one of the $new_names).
        
        :param array $new_names: Names of the tags this one should be renamed to.