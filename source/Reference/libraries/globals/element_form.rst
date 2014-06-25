.. _felementform:

#######################################################################
``element_form`` — Get the HTML for a form input for a given Element.
#######################################################################

:doc:`Form-related functions </Reference/packages/Function/View/Form/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/element_form.rst

.. php:function:: element_form($element, $record, $options = array())

    Get the HTML for a form input for a given Element.
    
    Assume that the given element has access to all of its values (for
    example,
    all values of a Title element for a given Item).
    
    This will output as many form inputs as there are values for a given
    element.
    In addition to that, it will give each set of inputs a label and a span
    with class="tooltip" containing the description for the element. This span
    can either be displayed, hidden with CSS or converted into a tooltip with
    javascript.
    
    All sets of form inputs for elements will be wrapped in a div with
    class="field".
    
    :type $element: Element|array
    :param $element:
    :type $record: Omeka_Record_AbstractRecord
    :param $record:
    :type $options: array
    :param $options:
    :returns: string HTML

*****
Usage
*****

.. include:: /Reference/libraries/globals/usage/element_form.rst

********
Examples
********

.. include:: /Reference/libraries/globals/examples/element_form.rst

********
See Also
********

.. include:: /Reference/libraries/globals/see_also/element_form.rst

