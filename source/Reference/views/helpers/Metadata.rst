--------------------------
Omeka_View_Helper_Metadata
--------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_Metadata

extends :php:class:`Zend_View_Helper_Abstract`

    Helper used to retrieve record metadata for for display.

    .. php:method:: metadata($record, $metadata, $options = array())

        Retrieve a specific piece of a record's metadata for display.

        :type $record: Omeka_Record_AbstractRecord
        :param $record: Database record representing the item from which to retrieve field data.
        :type $metadata: string|array
        :param $metadata: The metadata field to retrieve. If a string, refers to a property of the record itself. If an array, refers to an Element: the first entry is the set name, the second is the element name.
        :type $options: array|string|int
        :param $options: Options for formatting the metadata for display. - Array options: - 'all': If true, return an array containing all values for the field. - 'delimiter': Return the entire set of metadata as a string, where entries are separated by the given delimiter. - 'index': Return the metadata entry at the given zero-based index. - 'no_escape' => If true, do not escape the resulting values for HTML entities. - 'no_filter': If true, return the set of metadata without running any of the filters. - 'snippet': Trim the length of each piece of text to the given length in characters. - Passing simply the string 'all' is equivalent to array('all' => true) - Passing simply an integer is equivalent to array('index' => [the integer])
        :returns: string|array|null Null if field does not exist for item. Array if certain options are passed.  String otherwise.

    .. php:method:: _getOptions($options)

        Options can sometimes be an integer or a string instead of an array,
        which functions as a handy shortcut for theme writers.  This converts
        the short form of the options into its proper array form.

        :type $options: string|int|array
        :param $options:
        :returns: array

    .. php:method:: _getText($record, $metadata)

        Retrieve the text associated with a given element or field of the record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $metadata: string|array
        :param $metadata:
        :returns: string|array Either an array of ElementText records or a string.

    .. php:method:: _getRecordMetadata($record, $specialValue)

        Retrieve record metadata that is not stored as ElementTexts.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $specialValue: string
        :param $specialValue: Field name.
        :returns: mixed

    .. php:method:: _getElementText($record, $elementSetName, $elementName)

        Retrieve the set of ElementText records that correspond to a given
        element set and element.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $elementSetName: string
        :param $elementSetName:
        :type $elementName: string
        :param $elementName:
        :returns: array Set of ElementText records.

    .. php:method:: _process($record, $metadata, $text, $snippet, $escape, $filter)

        Process an individual piece of text.

        If given an ElementText record, the actual text string will be extracted
        automatically.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $metadata: string|array
        :param $metadata:
        :type $text: string|ElementText
        :param $text: Text to process.
        :type $snippet: int|bool
        :param $snippet: Snippet length, or false if no snippet.
        :type $escape: bool
        :param $escape: Whether to HTML escape the text.
        :type $filter: bool
        :param $filter: Whether to pass the output through plugin filters.
        :returns: string

    .. php:method:: _filterText($record, $metadata, $text, $elementText)

        Apply filters to a text value.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $metadata: string|array
        :param $metadata:
        :type $text: string
        :param $text:
        :type $elementText: ElementText|bool
        :param $elementText:
        :returns: string
