--------------------------------------
Omeka_Output_OmekaXml_AbstractOmekaXml
--------------------------------------

Package: :doc:`Output </Reference/packages/Output/index>`

.. php:class:: Omeka_Output_OmekaXml_AbstractOmekaXml

    Abstract base class for creating omeka-xml output formats.

    .. php:const:: XMLNS_XSI

        XML Schema instance namespace URI.

    .. php:const:: XMLNS

        Omeka-XML namespace URI.

    .. php:const:: XMLNS_SCHEMALOCATION

        Omeka-XML XML Schema URI.

    .. php:attr:: _record

        protected array|Omeka_Record_AbstractRecord

        This class' contextual record(s).

    .. php:attr:: _context

        protected string

        The context of this DOMDocument. Determines how buildNode() builds the
        elements. Valid contexts include: item, file.

    .. php:attr:: _doc

        protected DOMDocument

        The final document object.

    .. php:attr:: _node

        protected DOMNode

        The node built and set in child::_buildNode()

    .. php:method:: _buildNode()

        Abstract method. child::_buildNode() should set self::$_node.

    .. php:method:: __construct($record, $context)

        :type $record: Omeka_Record_AbstractRecord|array
        :param $record:
        :type $context: string
        :param $context: The context of this DOM document.

    .. php:method:: getDoc()

        Get the document object.

        :returns: DOMDocument

    .. php:method:: _setRootElement($rootElement)

        Set an element as root.

        :type $rootElement: DOMElement
        :param $rootElement:
        :returns: DOMElement The root element, including required attributes.

    .. php:method:: _createElement($name, $value = null, $id = null, $parentElement = null)

        Create a DOM element.

        :type $name: string
        :param $name: The name of the element.
        :param $value:
        :param $id:
        :param $parentElement:
        :returns: DOMElement

    .. php:method:: _setContainerPagination(DOMElement $parentElement)

        Set the pagination node for container elements

        :type $parentElement: DOMElement
        :param $parentElement:
        :returns: void

    .. php:method:: _getElemetSetsByElementTexts(Omeka_Record_AbstractRecord $record, $getItemType = false)

        Get all element sets, elements, and element texts associated with the
        provided record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record: The record from which to extract metadata.
        :type $getItemType: bool
        :param $getItemType: Whether to get the item type metadata.
        :returns: stdClass A list of element sets or an item type.

    .. php:method:: _buildElementSetContainerForRecord(Omeka_Record_AbstractRecord $record, DOMElement $parentElement)

        Build an elementSetContainer element in a record (item or file) context.

        :type $record: Omeka_Record_AbstractRecord
        :param $record: The record from which to build element sets.
        :type $parentElement: DOMElement
        :param $parentElement: The element set container will append to this element.
        :returns: void|null

    .. php:method:: _buildItemTypeForItem(Item $item, DOMElement $parentElement)

        Build an itemType element in an item context.

        :type $item: Item
        :param $item: The item from which to build the item type.
        :type $parentElement: DOMElement
        :param $parentElement: The item type will append to this element.
        :returns: void|null

    .. php:method:: _buildFileContainerForItem(Item $item, DOMElement $parentElement)

        Build a fileContainer element in an item context.

        :type $item: Item
        :param $item: The item from which to build the file container.
        :type $parentElement: DOMElement
        :param $parentElement: The file container will append to this element.
        :returns: void|null

    .. php:method:: _buildCollectionForItem(Item $item, DOMElement $parentElement)

        Build a collection element in an item context.

        :type $item: Item
        :param $item: The item from which to build the collection.
        :type $parentElement: DOMElement
        :param $parentElement: The collection will append to this element.
        :returns: void|null

    .. php:method:: _buildTagContainerForItem(Item $item, DOMElement $parentElement)

        Build a tagContainer element in an item context.

        :type $item: Item
        :param $item: The item from which to build the tag container.
        :type $parentElement: DOMElement
        :param $parentElement: The tag container will append to this element.
        :returns: void|null

    .. php:method:: _buildItemContainerForCollection(Collection $collection, DOMElement $parentElement)

        Build an itemContainer element in a collection context.

        :type $collection: Collection
        :param $collection: The collection from which to build the item container.
        :type $parentElement: DOMElement
        :param $parentElement: The item container will append to this element.
        :returns: void|null

    .. php:method:: _buildTagUri()

        Create a Tag URI to uniquely identify this Omeka XML instance.

        :returns: string

    .. php:method:: _buildUrl()

        Create a absolute URI containing the current query string.

        :returns: string
