-----------
ElementText
-----------

.. php:class:: ElementText

    Package: :doc:`Record </Reference/packages/Record/index>`

    An element text and its metadata.

    .. php:attr:: record_id
    
        ID of the associated record.

    .. php:attr:: record_type
    
        Type of the associated record.

    .. php:attr:: element_id
    
        ID of this text's Element.

    .. php:attr:: html
    
        Whether this text is HTML.

    .. php:attr:: text
    
        The text itself.

    .. php:method:: _validate()
    
        Validate the element text prior to saving.
        
        Test for a positive record_id and element_id, and a non-empty record_type.

    .. php:method:: __toString()
    
        Use the actual text when printing an ElementText as a string.
        
        :returns: string

    .. php:method:: setText(string $text)
    
        Set the text.
        
        :param string $text:

    .. php:method:: getText()
    
        Get the text.
        
        :returns: string

    .. php:method:: isHtml()
    
        Get whether this text is HTML.
        
        :returns: bool