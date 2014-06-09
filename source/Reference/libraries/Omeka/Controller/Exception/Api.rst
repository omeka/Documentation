------------------------------
Omeka_Controller_Exception_Api
------------------------------

.. php:class:: Omeka_Controller_Exception_Api

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    API exception.
    
    API implementers should throw this exception for controller errors.

    .. php:attr:: _errors
    


    .. php:attr:: message
    


    .. php:attr:: string
    


    .. php:attr:: code
    


    .. php:attr:: file
    


    .. php:attr:: line
    


    .. php:attr:: trace
    


    .. php:attr:: previous
    


    .. php:method:: __construct(string $message, int $code, array $errors)
    
        :param string $message: 
        :param int $code: 
        :param array $errors: Custom errors

    .. php:method:: getErrors()
    
        :returns: array

    .. php:method:: __clone()

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()