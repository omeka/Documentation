-----------------------------
Omeka_View_Helper_ElementForm
-----------------------------

.. php:class:: Omeka_View_Helper_ElementForm

    Generate the form markup for entering element text metadata.

    .. php:attr:: _element
    
        Displays a form for the record's element.
        
        The function applies filters that allow plugins to customize the display of element form components.
        Here is an example of how a plugin may add and implement an element form filter:
        
        add_filter(array('ElementForm', 'Item', 'Dublin Core', 'Title')), 'form_item_title');function form_item_title(array
        $components, $args){
        
        // Where $components would looks like://  array(//      'label' => [...],//      'inputs' => [...],//     
        'description' => [...],//      'comment' => [...],//      'add_input' => [...],//  )// and $args looks like:// 
        array(//      'record' => [...],//      'element' => [...],//      'options' => [...],//  )}

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

    .. php:method:: _getInputsComponent($extraFieldCount)
    
        :param unknown $extraFieldCount:

    .. php:method:: _getDescriptionComponent()

    .. php:method:: _getCommentComponent()

    .. php:method:: _getLabelComponent()