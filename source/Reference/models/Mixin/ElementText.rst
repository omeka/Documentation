-----------------
Mixin_ElementText
-----------------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_ElementText

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    Record mixin class for associating elements, element texts and their
    corresponding behaviors to a record.

    .. php:attr:: _textsByNaturalOrder

        protected array

        ElementText records stored in the order they were retrieved from the
        database.

    .. php:attr:: _textsByElementId

        protected array

        ElementText records indexed by the element_id.

    .. php:attr:: _elementsBySet

        protected array

        Element records indexed by set name and element name, so it looks like:

        $elements['Dublin Core']['Title'] = Element instance;

    .. php:attr:: _elementsById

        protected array

        Element records indexed by ID.

    .. php:attr:: _elementsOnForm

        protected array

        List of elements that were output on the form.  This can be used to
        determine the DELETE SQL to use to reset the elements when saving the
        form.

    .. php:attr:: _textsToSave

        protected array

        Set of ElementText records to save when submitting the form.  These will
        only be saved to the database if they successfully validate.

    .. php:attr:: _recordsAreLoaded

        protected bool

        Whether the elements and texts have been loaded yet.

    .. php:attr:: _replaceElementTexts

        protected bool

        Flag to indicate whether elements added to this save will replace
        existing element texts, not add them.

    .. php:method:: afterSave($args)

        Omeka_Record_AbstractRecord callback for afterSave. Saves the ElementText
        records once the associated record is saved. Adds the record's element
        texts to the search text.

        :param $args:

    .. php:method:: _getDb()

        Get the database object from the associated record.

        :returns: Omeka_Db

    .. php:method:: _getRecordType()

        Get the class name of the associated record (Item, File, etc.).

        :returns: string Type of record

    .. php:method:: loadElementsAndTexts($reload = false)

        Load all the ElementText records for the given record (Item, File, etc.).
        These will be indexed by [element_id].

        Also load all the Element records and index those by their name and set
        name.

        :type $reload: boolean
        :param $reload: Whether or not reload all the data that was previously loaded.
        :returns: void

    .. php:method:: _loadElements($reload = false)

        :param $reload:

    .. php:method:: _getElementTextRecords()

        Retrieve all of the ElementText records for the given record.

        :returns: array Set of ElementText records for the record.

    .. php:method:: _getElementRecords()

        Retrieve all of the Element records for the given record.

        :returns: array All Elements that apply to the record's type.

    .. php:method:: getElementTextsByRecord($element)

        Retrieve all of the record's ElementTexts for the given Element.

        :type $element: Element
        :param $element:
        :returns: array Set of ElementText records.

    .. php:method:: getElementTexts($elementSetName, $elementName)

        Retrieve all of the record's ElementTexts for the given element name and
        element set name.

        :type $elementSetName: string
        :param $elementSetName: Element set name
        :type $elementName: string
        :param $elementName: Element name
        :returns: array Set of ElementText records.

    .. php:method:: getAllElementTexts()

        Retrieve all of the record's ElementTexts, in order.

        :returns: array Set of ElementText records.

    .. php:method:: getAllElementTextsByElement()

        Retrieve all of the record's ElementTexts, indexed by element ID.

        :returns: array Set of ElementText records, indexed by element_id.

    .. php:method:: getElementsBySetName($elementSetName)

        Retrieve the Element records for the given ElementSet.

        :param $elementSetName:
        :returns: array Set of Element records

    .. php:method:: getAllElements()

        Retrieve ALL the Element records for the object, organized by ElementSet.
        For example, $elements['Dublin Core'] = array(Element instance, Element
        instance, ...)

        :returns: array Set of Element records

    .. php:method:: getElement($elementSetName, $elementName)

        Retrieve the Element record corresponding to the given element name and
        element set name.

        :type $elementSetName: string
        :param $elementSetName:
        :type $elementName: string
        :param $elementName:
        :returns: Element

    .. php:method:: getElementById($elementId)

        Retrieve the Element with the given ID.

        :type $elementId: int
        :param $elementId:
        :returns: Element

    .. php:method:: _indexTextsByElementId($textRecords)

        Index a set of ElementTexts based on element ID.

        :type $textRecords: array
        :param $textRecords: Set of ElementText records
        :returns: array The provided ElementTexts, indexed by element ID.

    .. php:method:: _indexElementsBySet($elementRecords)

        Index a set of Elements based on their name. The result is a doubly
        associative array, with the first key being element set name and the
        second
        being element name.

        i.e., $indexed['Dublin Core']['Creator'] = Element instance

        :type $elementRecords: array
        :param $elementRecords: Set of Element records
        :returns: array The provided Elements, indexed as described

    .. php:method:: _indexElementsById($elementRecords)

        Indexes the elements returned by element ID.

        :param $elementRecords:
        :returns: array

    .. php:method:: addTextForElement($element, $elementText, $isHtml = false)

        Add a string of text for an element.

        Creates a new ElementText record, populates it with the specified text
        value and assigns it to the element.

        saveElementTexts() must be called after this in order to save the element
        texts to the database.

        :type $element: Element
        :param $element: Element which text should be created for
        :type $elementText: string
        :param $elementText: Text to be added
        :type $isHtml: bool
        :param $isHtml: Whether the text to add is HTML

    .. php:method:: addElementTextsByArray($elementTexts)

        Add element texts for a record based on a formatted array of values.
        The array must be formatted as follows:

        <code>
        'Element Set Name' =>
        array('Element Name' =>
        array(array('text' => 'foo', 'html' => false)))
        </code>

        Since 1.4, the array can also be formatted thusly:

        <code>
        array(
        array('element_id' => 1,
        'text' => 'foo',
        'html' => false)
        )
        </code>

        :type $elementTexts: array
        :param $elementTexts:

    .. php:method:: _addTextsByElementName($elementTexts)

        :param $elementTexts:

    .. php:method:: _addTextsByElementId($texts)

        :param $texts:

    .. php:method:: beforeSaveElements($post)

        The application flow is thus:

        1) Build ElementText objects from the POST.
        2) Validate the ElementText objects and assign error messages if
        necessary.
        3) After the item saves correctly, delete all the ElementText records for
        the Item.
        4) Save the new ElementText objects to the database.

        :param $post:

    .. php:method:: _getElementTextsToSaveFromPost($post)

        The POST should have a key called "Elements" that contains an array
        that is keyed to an element's ID.  That array should contain all the
        text values for that element. For example:

        <code>

        array('Elements' =>
        array(
        '50' => array(array('text' => 'Foobar', //element id 50, e.g. DC:Title
        'html' => 0
        )),
        '41' => array(array('text' => '<p>Baz baz baz</p>', //element id 41, e.g.
        DC:Description
        'html' => 1
        ))
        )
        )

        </code>

        :param $post:

    .. php:method:: getTextStringFromFormPost($postArray, $element)

        Retrieve a text string for an element from POSTed form data.

        :param $postArray:
        :param $element:
        :returns: string

    .. php:method:: _validateElementTexts()

        Validate all the elements one by one.  This is potentially a lot slower
        than batch processing the form, but it gives the added bonus of being
        able to encapsulate the logic for validation of Elements.

    .. php:method:: _elementTextIsValid($elementTextRecord)

        Return whether the given ElementText record is valid.

        :type $elementTextRecord: ElementText
        :param $elementTextRecord:
        :returns: boolean

    .. php:method:: setReplaceElementTexts($replaceElementTexts = true)

        Set the flag to indicate whether elements added to this save will replace
        existing element texts, not add them.

        :param $replaceElementTexts:

    .. php:method:: saveElementTexts()

        Save all ElementText records that were associated with a record.

        Typically called in the afterSave() hook for a record.

    .. php:method:: deleteElementTextsByElementId($elementIdArray = array())

        Delete all the element texts for element_id's that have been provided.

        :param $elementIdArray:
        :returns: boolean

    .. php:method:: deleteElementTexts()

        Delete all the element texts assigned to the current record ID.

        :returns: boolean

    .. php:method:: hasElementText($elementSetName, $elementName)

        Returns whether or not the record has at least 1 element text

        :type $elementSetName: string
        :param $elementSetName: Element set name
        :type $elementName: string
        :param $elementName: Element name
        :returns: boolean

    .. php:method:: getElementTextCount($elementSetName, $elementName)

        Returns the number of element texts for the record

        :type $elementSetName: string
        :param $elementSetName: Element set name
        :type $elementName: string
        :param $elementName: Element name
        :returns: boolean

    .. php:method:: getDisplayTitle($default = null)

        Return the title of this record for display/interface purposes

        If no title is present or the title contains no text, returns the passed
        $default value.
        If no $default is given, returns the translated string [Untitled].

        :param $default:
        :returns: string Raw (unescaped) title string for the record.
