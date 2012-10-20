----------------------------
Omeka_Db_Migration_Exception
----------------------------

.. php:class:: Omeka_Db_Migration_Exception

    Package: :doc:`/Reference/packages/Db\Migration/index`

    Indicates an error during the database migration process.

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