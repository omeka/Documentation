-----------------------------
Omeka_View_Helper_ElementForm
-----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_ElementForm

extends :php:class:`Zend_View_Helper_Abstract`

    Generate the form markup for entering element text metadata.

    .. php:attr:: _element

        protected Element

        Displays a form for the record's element.

        The function applies filters that allow plugins to customize the display
        of element form components.
        Here is an example of how a plugin may add and implement an element form
        filter:

        add_filter(array('ElementForm', 'Item', 'Dublin Core', 'Title')),
        'form_item_title');
        function form_item_title(array $components, $args)
        {

        // Where $components would looks like:
        //  array(
        //      'label' => [...],
        //      'inputs' => [...],
        //      'description' => [...],
        //      'comment' => [...],
        //      'add_input' => [...],
        //  )
        // and $args looks like:
        //  array(
        //      'record' => [...],
        //      'element' => [...],
        //      'options' => [...],
        //  )
        }

    .. php:attr:: _record

        protected

    .. php:method:: elementForm(Element $element, Omeka_Record_AbstractRecord $record, $options = array())

        :type $element: Element
        :param $element:
        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :param $options:

    .. php:method:: _getFieldLabel()

    .. php:method:: _getFieldDescription()

    .. php:method:: _getFieldComment()

    .. php:method:: _isPosted()

    .. php:method:: _getPostArray()

    .. php:method:: _getFormFieldCount()

        How many form inputs to display for a given element.

        :returns: int

    .. php:method:: _getPostValueForField($index)

        :param $index:
        :returns: mixed

    .. php:method:: _getHtmlFlagForField($index)

        :param $index:

    .. php:method:: _getValueForField($index)

        Retrieve the form value for the field.

        :param $index:
        :returns: string

    .. php:method:: getElementTexts($index = null)

        If index is not given, return all texts.

        :param $index:

    .. php:method:: _getInputsComponent($extraFieldCount = null)

        :param $extraFieldCount:

    .. php:method:: _getDescriptionComponent()

    .. php:method:: _getCommentComponent()

    .. php:method:: _getLabelComponent()
