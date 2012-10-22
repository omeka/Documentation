---------------------------------
Omeka_View_Helper_AllElementTexts
---------------------------------

.. php:class:: Omeka_View_Helper_AllElementTexts

    Package: :doc:`/Reference/packages/View\Helper/index`

    View helper for retrieving lists of metadata for any record that uses 
    Mixin_ElementText.

    .. php:attr:: _record
    
        The record being printed.

    .. php:attr:: _showEmptyElements
    
        Flag to indicate whether to show elements that do not have text.

    .. php:attr:: _emptyElementString
    
        String to display if elements without text are shown.

    .. php:attr:: _elementSetsToShow
    
        Element sets to list.

    .. php:attr:: _returnType
    
        Type of data to return.

    .. php:attr:: _partial
    
        Path for the view partial.

    .. php:method:: allElementTexts(Omeka_Record_AbstractRecord|string $record, array $options = Array)
    
        Get the record metadata list.
        
        :param Omeka_Record_AbstractRecord|string $record: Record to retrieve metadata from.
        :param array $options: Available options: - show_empty_elements' => bool|string Whether to show elements that do not contain text. A string will set self::$_showEmptyElements to true and set self::$_emptyElementString to the provided string. - 'show_element_sets' => array List of names of element sets to display. - 'return_type' => string 'array', 'html'.  Defaults to 'html'.
        :returns: string|array

    .. php:method:: _setOptions(array $options)
    
        Set the options.
        
        :param array $options: 
        :returns: void

    .. php:method:: _getElementsBySet()
    
        Get an array of all element sets containing their respective elements.
        
        :returns: array

    .. php:method:: _filterItemTypeElements(array $elementsBySet)
    
        Filter the display of the Item Type element set, if present.
        
        :param array $elementsBySet: 
        :returns: array

    .. php:method:: _elementIsShowable(Element $element, array $texts)
    
        Determine if an element is allowed to be shown.
        
        :param Element $element: 
        :param array $texts: 
        :returns: boolean

    .. php:method:: _getFormattedElementTexts(Omeka_Record_AbstractRecord $record, array $metadata)
    
        Return a formatted version of all the texts for the requested element.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param array $metadata: 
        :returns: array

    .. php:method:: _getOutputAsHtml()
    
        Output the default HTML format for displaying record metadata.
        
        :returns: string

    .. php:method:: _getOutputAsArray()
    
        Get the metadata list as a PHP array.
        
        :returns: array

    .. php:method:: _getOutput()
    
        Get the metadata list.
        
        :returns: string|array

    .. php:method:: _loadViewPartial(array $vars = Array)
    
        Load a view partial to display the data.
        
        :param array $vars: Variables to pass to the partial.
        :returns: string