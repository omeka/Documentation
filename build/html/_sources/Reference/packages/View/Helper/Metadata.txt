--------------------------
Omeka_View_Helper_Metadata
--------------------------

.. php:class:: Omeka_View_Helper_Metadata

    Package: :doc:`/Reference/packages/View\Helper/index`

    Helper used to retrieve record metadata for for display.

    .. php:attr:: _record
    


    .. php:attr:: _metadata
    


    .. php:method:: metadata(Omeka_Record_AbstractRecord $record, string|array $metadata, array|string|integer $options = Array)
    
        Retrieve a specific piece of a record's metadata for display.
        
        :param Omeka_Record_AbstractRecord $record: Database record representing the item from which to retrieve field data.
        :param string|array $metadata: The metadata field to retrieve. If a string, refers to a property of the record itself. If an array, refers to an Element: the first entry is the set name, the second is the element name.
        :param array|string|integer $options: Options for formatting the metadata for display. - Array options: - 'all': If true, return an array containing all values for the field. - 'delimiter': Return the entire set of metadata as a string, where entries are separated by the given delimiter. - 'index': Return the metadata entry at the given zero-based index. - 'no_escape' => If true, do not escape the resulting values for HTML entities. - 'no_filter': If true, return the set of metadata without running any of the filters. - 'snippet': Trim the length of each piece of text to the given length in characters. - Passing simply the string 'all' is equivalent to array('all' => true) - Passing simply an integer is equivalent to array('index' => [the integer])
        :returns: string|array|null Null if field does not exist for item. Array if certain options are passed.  String otherwise.

    .. php:method:: _getOptions(string|integer|array $options)
    
        Options can sometimes be an integer or a string instead of an array,
        which functions as a handy shortcut for theme writers.  This converts
        the short form of the options into its proper array form.
        
        :param string|integer|array $options: 
        :returns: array

    .. php:method:: _getText(Omeka_Record_AbstractRecord $record, string|array $metadata)
    
        Retrieve the text associated with a given element or field of the record.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param string|array $metadata: 
        :returns: string|array Either an array of ElementText records or a string.

    .. php:method:: _getRecordMetadata(Omeka_Record_AbstractRecord $record, string $specialValue)
    
        Retrieve record metadata that is not stored as ElementTexts.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param string $specialValue: Field name.
        :returns: mixed

    .. php:method:: _getElementText(Omeka_Record_AbstractRecord $record, string $elementSetName, string $elementName)
    
        Retrieve the set of ElementText records that correspond to a given
        element set and element.
        
        :param Omeka_Record_AbstractRecord $record: 
        :param string $elementSetName: 
        :param string $elementName: 
        :returns: array Set of ElementText records.

    .. php:method:: _process(string|ElementText $text, int|bool $snippet, bool $escape, bool $filter)
    
        Process an individual piece of text.
        
        If given an ElementText record, the actual text string will beextracted automatically.
        
        :param string|ElementText $text: Text to process.
        :param int|bool $snippet: Snippet length, or false if no snippet.
        :param bool $escape: Whether to HTML escape the text.
        :param bool $filter: Whether to pass the output through plugin filters.
        :returns: string

    .. php:method:: _filterText(string $text, ElementText|bool $elementText)
    
        Apply filters to a text value.
        
        :param string $text: 
        :param ElementText|bool $elementText: 
        :returns: string