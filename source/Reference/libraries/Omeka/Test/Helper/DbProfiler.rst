----------------------------
Omeka_Test_Helper_DbProfiler
----------------------------

Package: :doc:`Test\\Helper </Reference/packages/Test/Helper/index>`

.. php:class:: Omeka_Test_Helper_DbProfiler

    Catch-all class for database helper methods that are shared across test cases.

    .. php:method:: __construct(Zend_Db_Profiler $profiler, PHPUnit_Framework_Assert $test)

        Constructor.

        :type $profiler: Zend_Db_Profiler
        :param $profiler:
        :type $test: PHPUnit_Framework_Assert
        :param $test:

    .. php:method:: assertDbQuery($sqlPart, $message = null)

        :param $sqlPart:
        :param $message:

    .. php:method:: assertTotalNumQueries($queryCount, $msg = null)

        Assert that the given number of SQL queries were made.

        :type $queryCount: integer
        :param $queryCount:
        :param $msg:
