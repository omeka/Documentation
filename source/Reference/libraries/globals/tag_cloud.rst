.. _ftagcloud:

#######################################################################################
``tag_cloud`` — Create a tag cloud made of divs that follow the hTagcloud microformat
#######################################################################################

:doc:`Tag-related functions </Reference/packages/Function/View/Tag/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/tag_cloud.rst

.. php:function:: tag_cloud($recordOrTags = null, $link = null, $maxClasses = 9, $tagNumber = false, $tagNumberOrder = null)

    Create a tag cloud made of divs that follow the hTagcloud microformat
    
    :type $recordOrTags: Omeka_Record_AbstractRecord|array
    :param $recordOrTags: The record to retrieve tags from, or the actual array of tags
    :type $link: string|null
    :param $link: The URI to use in the link for each tag. If none given, tags in the cloud will not be given links.
    :type $maxClasses: int
    :param $maxClasses:
    :type $tagNumber: bool
    :param $tagNumber:
    :type $tagNumberOrder: string
    :param $tagNumberOrder:
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

