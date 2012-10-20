------------------------------------
Omeka_Db_Migration_AbstractMigration
------------------------------------

.. php:class:: Omeka_Db_Migration_AbstractMigration

    Package: :doc:`/Reference/packages/Db\Migration/index`

    Database migration classes may inherit from this one.

    .. php:attr:: db
    


    .. php:method:: setDb(Omeka_Db $db)
    
        Set the database to migrate.
        
        :param Omeka_Db $db: 
        :returns: void

    .. php:method:: getDb()
    
        :returns: Omeka_Db

    .. php:method:: down()
    
        Template method for reversing the migration.
        
        This is defined as a template method instead of leaving it abstract becausepre-existing implementations of
        Omeka_Db_Migration were not required toimplement the down() method.  This ensures backwards compatibility forthose
        migrations.

    .. php:method:: __call(string $m, array $a)
    
        Proxy calls to Omeka_Db.
        
        Allows migration writers to call db methods directly on $this.
        
        :param string $m: Method name.
        :param array $a: Method arguments.

    .. php:method:: form()
    
        If the migration requires a form submission, here's where to handle display of it
        
        :returns: void

    .. php:method:: up()