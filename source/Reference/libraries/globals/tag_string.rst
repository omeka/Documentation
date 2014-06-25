.. _ftagstring:

################################################################################
``tag_string`` — Return a tag string given an Item, Exhibit, or a set of tags.
################################################################################

:doc:`Tag-related functions </Reference/packages/Function/View/Tag/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/tag_string.rst

.. php:function:: tag_string($recordOrTags = null, $link = 'items/browse', $delimiter = null)

    Return a tag string given an Item, Exhibit, or a set of tags.
    
    :type $recordOrTags: Omeka_Record_AbstractRecord|array
    :param $recordOrTags: The record to retrieve tags from, or the actual array of tags
    :type $link: string|null
    :param $link: The URL to use for links to the tags (if null, tags aren't linked)
    :type $delimiter: string
    :param $delimiter: ', ' (comma and whitespace) is the default tag_delimiter option. Configurable in Settings
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/tag_string.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/tag_string.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/tag_string.rst

