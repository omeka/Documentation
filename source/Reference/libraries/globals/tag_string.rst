##########
tag_string
##########

.. php:function:: tag_string(Omeka_Record_AbstractRecord|array $recordOrTags, string|null $link = items/browse, string $delimiter)

    Return a tag string given an Item, Exhibit, or a set of tags.
    
    :param Omeka_Record_AbstractRecord|array $recordOrTags: The record to retrieve tags from, or the actual array of tags
    :param string|null $link: The URL to use for links to the tags (if null, tags aren't linked)
    :param string $delimiter: ', ' (comma and whitespace) by default
    :returns: string HTML

*****
Usage
*****



********
Examples
********



