------------------------------
Omeka_View_Helper_ElementInput
------------------------------

.. php:class:: Omeka_View_Helper_ElementInput

    Generate the form markup for entering one HTML input for an Element.

    .. php:attr:: _element
    
        Element record to display the input for.

    .. php:attr:: _record
    
        Omeka_Record_AbstractRecord to display the input for.

    .. php:method:: elementInput(Element $element, Omeka_Record_AbstractRecord $record, int $index = 0, string $value = , bool $isHtml = )
    
        Display one form input for an Element.
        
        :param Element $element: The Element to display the input for.
        :param Omeka_Record_AbstractRecord $record: The record to display the input for.
        :param int $index: The index of this input. (starting at zero).
        :param string $value: The default value of this input.
        :param bool $isHtml: Whether this input's value is HTML.
        :returns: string

    .. php:method:: _getInputComponent(string $inputNameStem, string $value)
    
        Get the actual HTML input for this Element.
        
        :param string $inputNameStem: 
        :param string $value: 
        :returns: string

    .. php:method:: _getControlsComponent()
    
        Get the button that will allow a user to remove this form input.
        The submit input has a class of 'add-element', which is used by the
        Javascript to do stuff.
        
        :returns: string

    .. php:method:: _getHtmlCheckboxComponent(string $inputNameStem, bool $isHtml)
    
        Get the HTML checkbox that lets users toggle the editor.
        
        :param string $inputNameStem: 
        :param bool $isHtml: 
        :returns: string