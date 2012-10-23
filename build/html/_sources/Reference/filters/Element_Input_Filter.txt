####################
Element Input Filter
####################

*****
Usage
*****

*****
Value
*****

``array`` $components

    The input components, like:
    
        .. code-block:: php
        
        $components = array(
            'input' => $this->_getInputComponent($inputNameStem, $value),
            'form_controls' => $this->_getControlsComponent(),
            'html_checkbox' => $this->_getHtmlCheckboxComponent($inputNameStem, $isHtml),
            'html' => null
        );

*********
Arguments
*********

``string`` input_name_stem

    The name of the input, e.g., ``Elements[1][0]``
    
``string`` value

    The value for the input
    
:php:class:`Omeka_Record_AbstractRecord` record

    The model being edited
    
:php:class:`Element` element

    The element being edited
    
``string`` index

    The index of the input for the element
    
``boolean`` is_html

    Whether the input uses html
    
    

********
Examples
********


