--------------------------------------
Omeka_Output_OmekaXml_AbstractOmekaXml
--------------------------------------

.. php:class:: Omeka_Output_OmekaXml_AbstractOmekaXml

    Abstract base class for creating omeka-xml output formats.

    .. php:const:: XMLNS_XSI
    
    
    
        XML Schema instance namespace URI.

    .. php:const:: XMLNS
    
    
    
        Omeka-XML namespace URI.

    .. php:const:: XMLNS_SCHEMALOCATION
    
    
    
        Omeka-XML XML Schema URI.

    .. php:attr:: _record
    
        This class' contextual record(s).

    .. php:attr:: _context
    
        The context of this DOMDocument. Determines how buildNode() builds the 
        elements. Valid contexts include: item, file.

    .. php:attr:: _doc
    
        The final document object.

    .. php:attr:: _node
    
        The node built and set in child::_buildNode()

    .. php:method:: _buildNode()
    
        Abstract method. child::_buildNode() should set self::$_node.

    .. php:method:: __construct(Omeka_Record_AbstractRecord|array $record, string $context)
    
        :param Omeka_Record_AbstractRecord|array $record: 
        :param string $context: The context of this DOM document.

    .. php:method:: getDoc()
    
        Get the document object.
        
        :returns: DOMDocument

    .. php:method:: _setRootElement(DOMElement $rootElement)
    
        Set an element as root.
        
        :param DOMElement $rootElement: 
        :returns: DOMElement The root element, including required attributes.

    .. php:method:: _createElement(string $name, $value, $id, $parentElement)
    
        Create a DOM element.
        
        :param string $name: The name of the element.
        :param unknown $value: 
        :param unknown $id: 
        :param unknown $parentElement: 
        :returns: DOMElement

    .. php:method:: _setContainerPagination(DOMElement $parentElement)
    
        Set the pagination node for container elements
        
        :param DOMElement $parentElement: 
        :returns: void

    .. php:method:: _getElemetSetsByElementTexts(Omeka_Record_AbstractRecord $record, bool $getItemType = )
    
        Get all element sets, elements, and element texts associated with the 
        provided record.
        
        :param Omeka_Record_AbstractRecord $record: The record from which to extract metadata.
        :param bool $getItemType: Whether to get the item type metadata.
        :returns: stdClass A list of element sets or an item type.

    .. php:method:: _buildElementSetContainerForRecord(Omeka_Record_AbstractRecord $record, DOMElement $parentElement)
    
        Build an elementSetContainer element in a record (item or file) context.
        
        :param Omeka_Record_AbstractRecord $record: The record from which to build element sets.
        :param DOMElement $parentElement: The element set container will append to this element.
        :returns: void|null

    .. php:method:: _buildItemTypeForItem(Item $item, DOMElement $parentElement)
    
        Build an itemType element in an item context.
        
        :param Item $item: The item from which to build the item type.
        :param DOMElement $parentElement: The item type will append to this element.
        :returns: void|null

    .. php:method:: _buildFileContainerForItem(Item $item, DOMElement $parentElement)
    
        Build a fileContainer element in an item context.
        
        :param Item $item: The item from which to build the file container.
        :param DOMElement $parentElement: The file container will append to this element.
        :returns: void|null

    .. php:method:: _buildCollectionForItem(Item $item, DOMElement $parentElement)
    
        Build a collection element in an item context.
        
        :param Item $item: The item from which to build the collection.
        :param DOMElement $parentElement: The collection will append to this element.
        :returns: void|null

    .. php:method:: _buildTagContainerForItem(Item $item, DOMElement $parentElement)
    
        Build a tagContainer element in an item context.
        
        :param Item $item: The item from which to build the tag container.
        :param DOMElement $parentElement: The tag container will append to this element.
        :returns: void|null

    .. php:method:: _buildItemContainerForCollection(Collection $collection, DOMElement $parentElement)
    
        Build an itemContainer element in a collection context.
        
        :param Collection $collection: The collection from which to build the item container.
        :param DOMElement $parentElement: The item container will append to this element.
        :returns: void|null

    .. php:method:: _buildTagUri()
    
        Create a Tag URI to uniquely identify this Omeka XML instance.
        
        :returns: string

    .. php:method:: _buildUrl()
    
        Create a absolute URI containing the current query string.
        
        :returns: string