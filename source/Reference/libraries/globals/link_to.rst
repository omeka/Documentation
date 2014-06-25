.. _flinkto:

##################################################
``link_to`` — Get a link to a page within Omeka.
##################################################

:doc:`Navigation-related functions </Reference/packages/Function/View/Navigation/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/link_to.rst

.. php:function:: link_to($record, $action = null, $text = null, $props = array(), $queryParams = array())

    Get a link to a page within Omeka.
    
    The controller and action can be manually specified, or if a record is
    passed this function will hand off to record_url to automatically get a
    link to that record (either its default action or one explicitly chosen).
    
    :type $record: Omeka_Record_AbstractRecord|string
    :param $record: The name of the controller to use for the link.  If a record instance is passed, then it inflects the name of the controller from the record class.
    :type $action: string
    :param $action: The action to use for the link
    :type $text: string
    :param $text: The text to put in the link.  Default is 'View'.
    :type $props: array
    :param $props: Attributes for the <a> tag
    :type $queryParams: array
    :param $queryParams: the parameters in the uri query
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/link_to.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/link_to.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/link_to.rst

