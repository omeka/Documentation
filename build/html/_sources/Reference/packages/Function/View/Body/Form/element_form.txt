############
element_form
############

:doc:`Form-related functions </Reference/packages/Function/View/Body/Form/index>`

*******
Summary
*******

.. include:: /Reference/libraries/globals/summary/element_form.rst

.. php:function:: element_form(Element|array $element, Omeka_Record_AbstractRecord $record, array $options = Array)

    Return the proper HTML for a form input for a given Element record.
    
    Assume that the given element has access to all of its values (for example,
    all values of a Title element for a given Item).
    
    This will output as many form inputs as there are values for a given element.In addition to that, it will give each
    set of inputs a label and a span withclass="tooltip" containing the description for the element. This span caneither
    be displayed, hidden with CSS or converted into a tooltip withjavascript.
    
    All sets of form inputs for elements will be wrapped in a div withclass="field".
    
    :param Element|array $element: 
    :param Omeka_Record_AbstractRecord $record: 
    :param array $options: 
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

