---------------
Omeka_Db_Select
---------------

.. php:class:: Omeka_Db_Select

    Package: Db

    Class for SQL SELECT generation and results.

    .. php:method:: __construct(Zend_Db_Adapter $adapter)
    
        :param Zend_Db_Adapter $adapter: (optional) Adapter to use instead of the one set up by Omeka.

    .. php:method:: hasJoin(string $name)
    
        Detect if this SELECT joins with the given table.
        
        :param string $name: Table name.
        :returns: boolean