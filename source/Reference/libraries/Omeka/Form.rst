----------
Omeka_Form
----------

Package: :doc:`Form </Reference/packages/Form/index>`

.. php:class:: Omeka_Form

extends :php:class:`Zend_Form`

    A Zend_Form subclass that sets up forms to be properly displayed in Omeka.

    .. php:attr:: _defaultDisplayGroupClass

        protected string

        Class name of Omeka DisplayGroup subclass.

    .. php:attr:: _autoApplyOmekaStyles

        protected bool

        Whether or not to automatically apply Omeka-specific decorators
        and styling information to form elements prior to rendering.

    .. php:method:: init()

        Set up Omeka-specific form elements and decorators.

    .. php:method:: loadDefaultDecorators()

        Set up base form decorators.

    .. php:method:: getDefaultElementDecorators()

        Return default decorators for form elements.

        Makes form output conform to Omeka conventions.

        :returns: array

    .. php:method:: applyOmekaStyles()

        Configure element styles / decorators based on the type of element.

        This may be called after elements to the form, as the decorator
        configuration in init() runs before elements can be added.

    .. php:method:: getMessagesAsString($messageDelimiter = '  ', $elementDelimiter = ', ')

        Retrieve all of the form error messages as a nicely formatted string.

        Useful for displaying all form errors at the top of a form, or for
        flashing form errors after redirects.

        :type $messageDelimiter: string
        :param $messageDelimiter: The string to display between different error messages for an element.
        :type $elementDelimiter: string
        :param $elementDelimiter: The string to display between different elements.
        :returns: string

    .. php:method:: setAutoApplyOmekaStyles($flag)

        Specify whether or not to automatically apply Omeka-specific decorators
        and styles prior to rendering the form.

        :type $flag: mixed
        :param $flag: A boolean or boolean-equivalent.

    .. php:method:: render(Zend_View_Interface $view = null)

        Apply Omeka default styles (if requested) just before rendering.

        :type $view: Zend_View_Interface
        :param $view:
        :returns: string

    .. php:method:: _addClassNameToElement(Zend_Form_Element $element, $className)

        Add a specific class name to an element.

        :type $element: Zend_Form_Element
        :param $element:
        :type $className: string
        :param $className:
