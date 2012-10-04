-----------------------------
Omeka_View_Helper_ElementForm
-----------------------------

.. php:class:: Omeka_View_Helper_ElementForm

    Generate the form markup for entering element text metadata.

    .. php:attr:: _element
    
        Element record to display the form for.

    .. php:attr:: _record
    


    .. php:method:: elementForm(Element $element, Omeka_Record_AbstractRecord $record, $options = Array)
    
        :param Element $element: 
        :param Omeka_Record_AbstractRecord $record: 
        :param unknown $options:

    .. php:method:: _getFieldLabel()

    .. php:method:: _getFieldDescription()

    .. php:method:: _getFieldComment()

    .. php:method:: _isPosted()

    .. php:method:: _getPostArray()

    .. php:method:: _getFormFieldCount()
    
        How many form inputs to display for a given element.
        
        :returns: integer

    .. php:method:: _getPostValueForField($index)
    
        :param unknown $index: 
        :returns: mixed

    .. php:method:: _getHtmlFlagForField($index)
    
        :param unknown $index:

    .. php:method:: _getValueForField($index)
    
        Retrieve the form value for the field.
        
        :param unknown $index: 
        :returns: string

    .. php:method:: getElementTexts($index)
    
        If index is not given, return all texts.
        
        :param unknown $index: 
        :returns: void

    .. php:method:: _displayFormFields($extraFieldCount)
    
        :param unknown $extraFieldCount:

    .. php:method:: _displayTooltip()

    .. php:method:: _displayFieldLabel()