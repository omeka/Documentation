-----------------------------------
Omeka_Job_Worker_InterruptException
-----------------------------------

.. php:class:: Omeka_Job_Worker_InterruptException

    Package: :doc:`/Reference/packages/Job\Worker/index`

    Exception thrown when the type of job could not be inferred from the message 
    passed to the factory.

    .. php:attr:: message
    


    .. php:attr:: string
    


    .. php:attr:: code
    


    .. php:attr:: file
    


    .. php:attr:: line
    


    .. php:attr:: trace
    


    .. php:attr:: previous
    


    .. php:method:: __clone()

    .. php:method:: __construct($message, $code, $previous)
    
        :param unknown $message: 
        :param unknown $code: 
        :param unknown $previous:

    .. php:method:: getMessage()

    .. php:method:: getCode()

    .. php:method:: getFile()

    .. php:method:: getLine()

    .. php:method:: getTrace()

    .. php:method:: getPrevious()

    .. php:method:: getTraceAsString()

    .. php:method:: __toString()