-----------------
Mixin_ElementText
-----------------

.. php:class:: Mixin_ElementText

    Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

    Record mixin class for associating elements, element texts and their
    corresponding behaviors to a record.

    .. php:attr:: _textsByNaturalOrder
    
        ElementText records stored in the order they were retrieved from the database.

    .. php:attr:: _textsByElementId
    
        ElementText records indexed by the element_id.

    .. php:attr:: _elementsBySet
    
        Element records indexed by set name and element name, so it looks like:
        
        $elements['Dublin Core']['Title'] = Element instance;

    .. php:attr:: _elementsById
    
        Element records indexed by ID.

    .. php:attr:: _elementsOnForm
    
        List of elements that were output on the form.  This can be used to 
        determine the DELETE SQL to use to reset the elements when saving the form.

    .. php:attr:: _textsToSave
    
        Set of ElementText records to save when submitting the form.  These will 
        only be saved to the database if they successfully validate.

    .. php:attr:: _recordsAreLoaded
    
        Whether the elements and texts have been loaded yet.

    .. php:attr:: _elementsByRecordType
    
        Sets of Element records indexed by record type.

    .. php:method:: afterSave($args)
    
        Omeka_Record_AbstractRecord callback for afterSave. Saves the ElementText 
        records once the associated record is saved. Adds the record's element 
        texts to the search text.
        
        :param unknown $args:

    .. php:method:: _getDb()
    
        Get the database object from the associated record.
        
        :returns: Omeka_Db

    .. php:method:: _getRecordType()
    
        Get the class name of the associated record (Item, File, etc.).
        
        :returns: string Type of record

    .. php:method:: loadElementsAndTexts(boolean $reload = )
    
        Load all the ElementText records for the given record (Item, File, etc.).
        These will be indexed by [element_id].
        
        Also load all the Element records and index those by their name and setname.
        
        :param boolean $reload: Whether or not reload all the data that was previously loaded.
        :returns: void

    .. php:method:: _loadElements($reload = )
    
        :param unknown $reload:

    .. php:method:: _getElementTextRecords()
    
        Retrieve all of the ElementText records for the given record.
        
        :returns: array Set of ElementText records for the record.

    .. php:method:: _getElementRecords()
    
        Retrieve all of the Element records for the given record.
        
        :returns: array All Elements that apply to the record's type.

    .. php:method:: getElementTextsByRecord(Element $element)
    
        Retrieve all of the record's ElementTexts for the given Element.
        
        :param Element $element: 
        :returns: array Set of ElementText records.

    .. php:method:: getElementTexts(string $elementSetName, string $elementName)
    
        Retrieve all of the record's ElementTexts for the given element name and
        element set name.
        
        :param string $elementSetName: Element set name
        :param string $elementName: Element name
        :returns: array Set of ElementText records.

    .. php:method:: getAllElementTexts()
    
        Retrieve all of the record's ElementTexts, in order.
        
        :returns: array Set of ElementText records.

    .. php:method:: getElementsBySetName($elementSetName)
    
        Retrieve the Element records for the given ElementSet.
        
        :param unknown $elementSetName: 
        :returns: array Set of Element records

    .. php:method:: getAllElements()
    
        Retrieve ALL the Element records for the object, organized by ElementSet.
        For example, $elements['Dublin Core'] = array(Element instance, Element instance, ...)
        
        :returns: array Set of Element records

    .. php:method:: getElement(string $elementSetName, string $elementName)
    
        Retrieve the Element record corresponding to the given element name and
        element set name.
        
        :param string $elementSetName: 
        :param string $elementName: 
        :returns: Element

    .. php:method:: getElementById(int $elementId)
    
        Retrieve the Element with the given ID.
        
        :param int $elementId: 
        :returns: Element

    .. php:method:: _indexTextsByElementId(array $textRecords)
    
        Index a set of ElementTexts based on element ID.
        
        :param array $textRecords: Set of ElementText records
        :returns: array The provided ElementTexts, indexed by element ID.

    .. php:method:: _indexElementsBySet(array $elementRecords)
    
        Index a set of Elements based on their name. The result is a doubly
        associative array, with the first key being element set name and the second
        being element name.
        
        i.e., $indexed['Dublin Core']['Creator'] = Element instance
        
        :param array $elementRecords: Set of Element records
        :returns: array The provided Elements, indexed as described

    .. php:method:: _indexElementsById($elementRecords)
    
        Indexes the elements returned by element ID.
        
        :param unknown $elementRecords: 
        :returns: array

    .. php:method:: addTextForElement(Element $element, string $elementText, bool $isHtml = )
    
        Add a string of text for an element.
        
        Creates a new ElementText record, populates it with the specified text value and assigns it to the element.
        
        saveElementTexts() must be called after this in order to save the elementtexts to the database.
        
        :param Element $element: Element which text should be created for
        :param string $elementText: Text to be added
        :param bool $isHtml: Whether the text to add is HTML

    .. php:method:: addElementTextsByArray($elementTexts)
    
        Add element texts for a record based on a formatted array of values.
        The array must be formatted as follows:
        
        .. code-block:: php 
        
        
        	                            'Element Set Name' => 
        	                                array('Element Name' => 
        	                                    array(array('text' => 'foo', 'html' => false)))
        
        
        Since 1.4, the array can also be formatted thusly:
        
        	               
        
        .. code-block:: php 
        
        
        	                    array(
        	                        array('element_id' => 1,
        	                              'text' => 'foo',
        	                              'html' => false)
        	                    )
        
        :param unknown $elementTexts:

    .. php:method:: _addTextsByElementName($elementTexts)
    
        :param unknown $elementTexts:

    .. php:method:: _addTextsByElementId($texts)
    
        :param unknown $texts:

    .. php:method:: beforeSaveElements($post)
    
        The application flow is thus:
        
        1) Build ElementText objects from the POST.2) Validate the ElementText objects and assign error messages ifnecessary.3) After the item saves correctly, delete all the ElementText recordsfor the Item.4) Save the new ElementText objects to the database.
        
        :param unknown $post:

    .. php:method:: _getElementTextsToSaveFromPost($post)
    
        The POST should have a key called "Elements" that contains an array
        that is keyed to an element's ID.  That array should contain all the 
        text values for that element. For example:
        
        <code>
        
        array('Elements' =>array('50' => array(array('text' => 'Foobar', //element id 50, e.g. DC:Title'html' => 0)),'41' => array(array('text' => '<p>Baz baz baz</p>', //element id 41, e.g. DC:Description'html' => 1))))
        
        </code>
        
        :param unknown $post:

    .. php:method:: getTextStringFromFormPost($postArray, $element)
    
        Retrieve a text string for an element from POSTed form data.
        
        :param unknown $postArray: 
        :param unknown $element: 
        :returns: string

    .. php:method:: _validateElementTexts()
    
        Validate all the elements one by one.  This is potentially a lot slower
        than batch processing the form, but it gives the added bonus of being 
        able to encapsulate the logic for validation of Elements.

    .. php:method:: _elementTextIsValid(ElementText $elementTextRecord)
    
        Return whether the given ElementText record is valid.
        
        :param ElementText $elementTextRecord: 
        :returns: boolean

    .. php:method:: saveElementTexts()
    
        Save all ElementText records that were associated with a record.
        
        Typically called in the afterSave() hook for a record.

    .. php:method:: deleteElementTextsByElementId($elementIdArray = Array)
    
        Delete all the element texts for element_id's that have been provided.
        
        :param unknown $elementIdArray: 
        :returns: boolean

    .. php:method:: deleteElementTexts()
    
        Delete all the element texts assigned to the current record ID.
        
        :returns: boolean

    .. php:method:: hasElementText(string $elementSetName, string $elementName)
    
        Returns whether or not the record has at least 1 element text
        
        :param string $elementSetName: Element set name
        :param string $elementName: Element name
        :returns: boolean

    .. php:method:: getElementTextCount(string $elementSetName, string $elementName)
    
        Returns the number of element texts for the record
        
        :param string $elementSetName: Element set name
        :param string $elementName: Element name
        :returns: boolean