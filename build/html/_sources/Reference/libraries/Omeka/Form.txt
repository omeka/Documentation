----------
Omeka_Form
----------

.. php:class:: Omeka_Form

    A Zend_Form subclass that sets up forms to be properly displayed in Omeka.

    .. php:attr:: _defaultDisplayGroupClass
    
        Class name of Omeka DisplayGroup subclass.

    .. php:attr:: _autoApplyOmekaStyles
    
        Whether or not to automatically apply Omeka-specific decorators
        and styling information to form elements prior to rendering.

    .. php:method:: init()
    
        Set up Omeka-specific form elements and decorators.
        
        :returns: void

    .. php:method:: loadDefaultDecorators()
    
        Set up base form decorators.
        
        :returns: void

    .. php:method:: getDefaultElementDecorators()
    
        Return default decorators for form elements.
        
        Makes form output conform to Omeka conventions.
        
        :returns: array

    .. php:method:: applyOmekaStyles()
    
        Configure element styles / decorators based on the type of element.
        
        This may be called after elements to the form, as the decorator configuration in init() runs before elements can be
        added.
        
        :returns: void

    .. php:method:: getMessagesAsString(string $messageDelimiter =   , string $elementDelimiter = , )
    
        Retrieve all of the form error messages as a nicely formatted string.
        
        Useful for displaying all form errors at the top of a form, or for flashing form errors after redirects.
        
        :param string $messageDelimiter: The string to display between different error messages for an element.
        :param string $elementDelimiter: The string to display between different elements.
        :returns: string

    .. php:method:: setAutoApplyOmekaStyles(mixed $flag)
    
        Specify whether or not to automatically apply Omeka-specific decorators
        and styles prior to rendering the form.
        
        :param mixed $flag: A boolean or boolean-equivalent.
        :returns: void

    .. php:method:: render(Zend_View_Interface $view)
    
        Apply Omeka default styles (if requested) just before rendering.
        
        :param Zend_View_Interface $view: 
        :returns: string

    .. php:method:: _addClassNameToElement(Zend_Form_Element $element, string $className)
    
        Add a specific class name to an element.
        
        :param Zend_Form_Element $element: 
        :param string $className: 
        :returns: void