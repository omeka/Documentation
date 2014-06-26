---------------------------------
Omeka_View_Helper_AllElementTexts
---------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_AllElementTexts

extends :php:class:`Zend_View_Helper_Abstract`

    View helper for retrieving lists of metadata for any record that uses
    Mixin_ElementText.

    .. php:attr:: _record

        protected Omeka_Record_AbstractRecord

        The record being printed.

    .. php:attr:: _showEmptyElements

        protected boolean

        Flag to indicate whether to show elements that do not have text.

    .. php:attr:: _showElementSetHeadings

        protected boolean

        Whether to include a heading for each Element Set.

    .. php:attr:: _emptyElementString

        protected string

        String to display if elements without text are shown.

    .. php:attr:: _elementSetsToShow

        protected array

        Element sets to list.

    .. php:attr:: _returnType

        protected string

        Type of data to return.

    .. php:attr:: _partial

        protected string

        Path for the view partial.

    .. php:method:: allElementTexts($record, $options = array())

        Get the record metadata list.

        :type $record: Omeka_Record_AbstractRecord|string
        :param $record: Record to retrieve metadata from.
        :type $options: array
        :param $options: Available options: - show_empty_elements' => bool|string Whether to show elements that do not contain text. A string will set self::$_showEmptyElements to true and set self::$_emptyElementString to the provided string. - 'show_element_sets' => array List of names of element sets to display. - 'return_type' => string 'array', 'html'.  Defaults to 'html'.
        :returns: string|array

    .. php:method:: _setOptions($options)

        Set the options.

        :type $options: array
        :param $options:
        :returns: void

    .. php:method:: _getElementsBySet()

        Get an array of all element sets containing their respective elements.

        :returns: array

    .. php:method:: _filterItemTypeElements($elementsBySet)

        Filter the display of the Item Type element set, if present.

        :type $elementsBySet: array
        :param $elementsBySet:
        :returns: array

    .. php:method:: _elementIsShowable(Element $element, $texts)

        Determine if an element is allowed to be shown.

        :type $element: Element
        :param $element:
        :type $texts: array
        :param $texts:
        :returns: boolean

    .. php:method:: _getFormattedElementTexts($record, $metadata)

        Return a formatted version of all the texts for the requested element.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :type $metadata: array
        :param $metadata:
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

    .. php:method:: _loadViewPartial($vars = array())

        Load a view partial to display the data.

        :type $vars: array
        :param $vars: Variables to pass to the partial.
        :returns: string
