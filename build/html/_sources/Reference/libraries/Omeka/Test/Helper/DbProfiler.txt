----------------------------
Omeka_Test_Helper_DbProfiler
----------------------------

.. php:class:: Omeka_Test_Helper_DbProfiler

    .. php:attr:: _profiler
    


    .. php:attr:: _test
    


    .. php:method:: __construct(Zend_Db_Profiler $profiler, PHPUnit_Framework_Assert $test)
    
        Constructor.
        
        :param Zend_Db_Profiler $profiler: 
        :param PHPUnit_Framework_Assert $test:

    .. php:method:: assertDbQuery($sqlPart, $message)
    
        :param unknown $sqlPart: 
        :param unknown $message:

    .. php:method:: assertTotalNumQueries(integer $queryCount, $msg)
    
        Assert that the given number of SQL queries were made.
        
        :param integer $queryCount: 
        :param unknown $msg: