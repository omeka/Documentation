-----------
ElementText
-----------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: ElementText

extends :php:class:`Omeka_Record_AbstractRecord`

    An element text and its metadata.

    .. php:attr:: record_id

        int

        ID of the associated record.

    .. php:attr:: record_type

        string

        Type of the associated record.

    .. php:attr:: element_id

        int

        ID of this text's Element.

    .. php:attr:: html

        int

        Whether this text is HTML.

    .. php:attr:: text

        string

        The text itself.

    .. php:method:: _validate()

        Validate the element text prior to saving.

        Test for a positive record_id and element_id, and a non-empty record_type.

    .. php:method:: __toString()

        Use the actual text when printing an ElementText as a string.

        :returns: string

    .. php:method:: setText($text)

        Set the text.

        :type $text: string
        :param $text:

    .. php:method:: getText()

        Get the text.

        :returns: string

    .. php:method:: isHtml()

        Get whether this text is HTML.

        :returns: bool
