-------------------------
Omeka_Validator_Exception
-------------------------

.. php:class:: Omeka_Validator_Exception

    Exception that is thrown when a form could not be validated correctly.

    .. php:attr:: _errors
    
        Message representing form errors.

    .. php:attr:: message
    


    .. php:attr:: string
    


    .. php:attr:: code
    


    .. php:attr:: file
    


    .. php:attr:: line
    


    .. php:attr:: trace
    


    .. php:attr:: previous
    


    .. php:method:: __construct($errors)
    
        :param unknown $errors: 
        :returns: void

    .. php:method:: getErrors()
    
        Get the error message that caused this exception.
        
        :returns: string

    .. php:method:: __clone()

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()