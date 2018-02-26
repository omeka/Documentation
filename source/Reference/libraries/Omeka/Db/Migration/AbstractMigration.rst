------------------------------------
Omeka_Db_Migration_AbstractMigration
------------------------------------

Package: :doc:`Db\\Migration </Reference/packages/Db/Migration/index>`

.. php:class:: Omeka_Db_Migration_AbstractMigration

implements :php:interface:`Omeka_Db_Migration_MigrationInterface`

    Database migration classes may inherit from this one.

    .. php:attr:: db

        protected

    .. php:method:: setDb(Omeka_Db $db)

        Set the database to migrate.

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: getDb()

        :returns: Omeka_Db

    .. php:method:: down()

        Template method for reversing the migration.

        This is defined as a template method instead of leaving it abstract
        because pre-existing implementations of Omeka_Db_Migration were not
        required to implement the down() method.  This ensures backwards
        compatibility for those migrations.

    .. php:method:: __call($m, $a)

        Proxy calls to Omeka_Db.

        Allows migration writers to call db methods directly on $this.

        :type $m: string
        :param $m: Method name.
        :type $a: array
        :param $a: Method arguments.

    .. php:method:: form()

        If the migration requires a form submission, here's where to handle
        display of it

    .. php:method:: up()
