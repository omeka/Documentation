---------
Mixin_Tag
---------

.. php:class:: Mixin_Tag

    Taggable
    Adaptation of the Rails Acts_as_taggable

    .. php:attr:: _tagTable
    


    .. php:attr:: _joinTable
    


    .. php:attr:: _type
    


    .. php:method:: __construct(Omeka_Record_AbstractRecord $record)
    
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: beforeDelete()
    
        Fires whenever deleting a record that is taggable
        This will actually delete all the references to a specific tag for a
        specific record
        
        :returns: void

    .. php:method:: afterSave($args)
    
        Add tags to this record's search text.
        
        :param unknown $args:

    .. php:method:: deleteTaggings()

    .. php:method:: getTaggings()
    
        Retrieve all the Taggings objects that represent between a specific tag
        and the current record
        Called by whatever record has enabled this module
        
        :returns: array of Taggings

    .. php:method:: getTags($order = Array)
    
        Get all the Tag records associated with this record
        
        :param unknown $order: 
        :returns: array of Tag

    .. php:method:: deleteTags(string|array $tags, string $delimiter)
    
        Delete a tag from the record
        
        :param string|array $tags: The tag name or array of tag names to delete from the record
        :param string $delimiter: The delimiter of the tags. Not applicable if $tags is an array
        :returns: bool Returns whether a tag in $tags was deleted. Returns false if $tags is empty. Returns true if at least one tag in $tags is deleted.

    .. php:method:: hasTag($tag)
    
        If the $tag were a string and the keys of Tags were just the names of the
        tags, this would be:
        in_array(array_keys($this->Tags))
        
        :param unknown $tag: 
        :returns: boolean

    .. php:method:: _getTagsFromString(string $string, $delimiter)
    
        Converts a delimited string of tags into an array of tag strings
        
        :param string $string: A delimited string of tags
        :param unknown $delimiter: 
        :returns: array An array of tag strings

    .. php:method:: addTags(array|string $tags, $delimiter)
    
        Add tags for the record
        
        :param array|string $tags: Either an array of tags or a delimited string
        :param unknown $delimiter: 
        :returns: void

    .. php:method:: diffTagString($string, $tags, $delimiter)
    
        Calculate the difference between a tag string and a set of tags
        
        :param unknown $string: 
        :param unknown $tags: 
        :param unknown $delimiter: 
        :returns: array Keys('removed','added')

    .. php:method:: applyTagString(string $string, $delimiter)
    
        This will add tags that are in the tag string and remove those that are no
        longer in the tag string
        
        :param string $string: A string of tags delimited by $delimiter
        :param unknown $delimiter: 
        :returns: void

