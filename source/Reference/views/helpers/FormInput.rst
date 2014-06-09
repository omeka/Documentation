---------------------------
Omeka_View_Helper_FormInput
---------------------------

.. php:class:: Omeka_View_Helper_FormInput

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    Helper for generic HTML5 input with settable type.

    .. php:method:: formInput(string|array $name, mixed $value, array $attribs)
    
        Generate an input element.
        
        :param string|array $name: If a string, the element name.  If an array, all other parameters are ignored, and the array elements are used in place of added parameters.
        :param mixed $value: The element value.
        :param array $attribs: Attributes for the element tag.
        :returns: string The element XHTML.