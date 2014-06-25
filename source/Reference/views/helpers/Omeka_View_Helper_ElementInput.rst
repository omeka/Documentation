------------------------------
Omeka_View_Helper_ElementInput
------------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_ElementInput

extends :php:class:`Zend_View_Helper_Abstract`

    Generate the form markup for entering one HTML input for an Element.

    .. php:attr:: _element

        protected Element

        Element record to display the input for.

    .. php:attr:: _record

        protected Omeka_Record_AbstractRecord

        Omeka_Record_AbstractRecord to display the input for.

    .. php:method:: elementInput(Element $element, Omeka_Record_AbstractRecord $record, $index = 0, $value = '', $isHtml = false)

        Display one form input for an Element.

        :type $element: Element
        :param $element: The Element to display the input for.
        :type $record: Omeka_Record_AbstractRecord
        :param $record: The record to display the input for.
        :type $index: int
        :param $index: The index of this input. (starting at zero).
        :type $value: string
        :param $value: The default value of this input.
        :type $isHtml: bool
        :param $isHtml: Whether this input's value is HTML.
        :returns: string

    .. php:method:: _getInputComponent($inputNameStem, $value)

        Get the actual HTML input for this Element.

        :type $inputNameStem: string
        :param $inputNameStem:
        :type $value: string
        :param $value:
        :returns: string

    .. php:method:: _getControlsComponent()

        Get the button that will allow a user to remove this form input.
        The submit input has a class of 'add-element', which is used by the
        Javascript to do stuff.

        :returns: string

    .. php:method:: _getHtmlCheckboxComponent($inputNameStem, $isHtml)

        Get the HTML checkbox that lets users toggle the editor.

        :type $inputNameStem: string
        :param $inputNameStem:
        :type $isHtml: bool
        :param $isHtml:
        :returns: string
