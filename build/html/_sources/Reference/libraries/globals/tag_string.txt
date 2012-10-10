##########
tag_string
##########

*******
Summary
*******

.. include:: summary/tag_string.rst

.. php:function:: tag_string(Omeka_Record_AbstractRecord|array $recordOrTags, string|null $link = items/browse, string $delimiter)

    Return a tag string given an Item, Exhibit, or a set of tags.
    
    :param Omeka_Record_AbstractRecord|array $recordOrTags: The record to retrieve tags from, or the actual array of tags
    :param string|null $link: The URL to use for links to the tags (if null, tags aren't linked)
    :param string $delimiter: ', ' (comma and whitespace) is the default tag_delimiter option. Configurable in Settings
    :returns: string HTML

*****
Usage
*****

.. include:: usage/tag_string.rst

********
Examples
********

.. include:: examples/tag_string.rst

********
See Also
********

.. include:: see_also/tag_string.rst

