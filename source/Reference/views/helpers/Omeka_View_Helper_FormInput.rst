---------------------------
Omeka_View_Helper_FormInput
---------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_FormInput

extends :php:class:`Zend_View_Helper_FormElement`

    Helper for generic HTML5 input with settable type.

    .. php:method:: formInput($name, $value = null, $attribs = null)

        Generate an input element.

        :type $name: string|array
        :param $name: If a string, the element name.  If an array, all other parameters are ignored, and the array elements are used in place of added parameters.
        :type $value: mixed
        :param $value: The element value.
        :type $attribs: array
        :param $attribs: Attributes for the element tag.
        :returns: string The element XHTML.
