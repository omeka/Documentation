---------------------------------
Omeka_Controller_Action_Helper_Db
---------------------------------

.. php:class:: Omeka_Controller_Action_Helper_Db

    An action helper replacement for the database-oriented methods that were 
    baked into Omeka_Controller_AbstractActionController in v1.x.

    .. php:attr:: _db
    


    .. php:attr:: _defaultTable
    


    .. php:attr:: _defaultModel
    


    .. php:attr:: _findByLimit
    


    .. php:method:: __construct(Omeka_Db $db)
    
        :param Omeka_Db $db:

    .. php:method:: init()

    .. php:method:: __call($method, $args)
    
        Delegate to the default table object for all other method calls.
        
        :param unknown $method: 
        :param unknown $args:

    .. php:method:: setDefaultModelName($modelName)
    
        Set the class name corresponding to the default model.
        
        :param unknown $modelName:

    .. php:method:: getDefaultModelName()

    .. php:method:: setDefaultTable(Omeka_Db_Table $table)
    
        :param Omeka_Db_Table $table:

    .. php:method:: getDb()

    .. php:method:: getTable(string|null $tableName)
    
        :param string|null $tableName: 
        :returns: Omeka_Db_Table

    .. php:method:: findById($id, $table)
    
        Find a particular record given its unique ID # and (optionally) its class name.
        
        :param unknown $id: 
        :param unknown $table: 
        :returns: Omeka_Record_AbstractRecord