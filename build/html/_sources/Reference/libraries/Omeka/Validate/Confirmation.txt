---------------------------
Omeka_Validate_Confirmation
---------------------------

.. php:class:: Omeka_Validate_Confirmation

    Package: :doc:`/Reference/packages/Validate/index`

    Adapted from Zend Framework documentation on custom validators.

    .. php:const:: NOT_MATCH
    
    
    
        Error message for non-matching confirmation.

    .. php:attr:: _field
    
        Field needing confirmation.

    .. php:attr:: _messageTemplates
    
        Error messages.

    .. php:attr:: _messageVariables
    
        Error message replace variables.

    .. php:method:: __construct($field)
    
        Sets validator options
        
        :param unknown $field:

    .. php:method:: isValid(string $value, string|array $context)
    
        Check that the value is valid.
        
        :param string $value: 
        :param string|array $context: 
        :returns: boolean

    .. php:method:: getField()
    
        Get the name of the field that needs confirmation.
        
        :returns: string

    .. php:method:: setField(string $field)
    
        Set the name of the field that needs confirmation.
        
        :param string $field: 
        :returns: void