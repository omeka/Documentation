.. _ftagcloud:

#########
tag_cloud
#########

:doc:`Tag-related functions </Reference/packages/Function/View/Tag/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/tag_cloud.rst

.. php:function:: tag_cloud(Omeka_Record_AbstractRecord|array $recordOrTags, string|null $link, int $maxClasses = 9, bool $tagNumber = , string $tagNumberOrder)

    Create a tag cloud made of divs that follow the hTagcloud microformat
    
    :param Omeka_Record_AbstractRecord|array $recordOrTags: The record to retrieve tags from, or the actual array of tags
    :param string|null $link: The URI to use in the link for each tag. If none given, tags in the cloud will not be given links.
    :param int $maxClasses: 
    :param bool $tagNumber: 
    :param string $tagNumberOrder: 
    :returns: string HTML for the tag cloud

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/tag_cloud.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/tag_cloud.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/tag_cloud.rst

