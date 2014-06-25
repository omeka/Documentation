--------------------------
Omeka_Db_Migration_Manager
--------------------------

Package: :doc:`Db\\Migration </Reference/packages/Db/Migration/index>`

.. php:class:: Omeka_Db_Migration_Manager

    Manages database migrations (both upgrades and downgrades).

    .. php:const:: MIGRATION_TABLE_NAME

        Name of the migrations table.

    .. php:const:: MIGRATION_DATE_FORMAT

        Formatting string to convert dates into YYYYMMDDHHMMSS pattern.

    .. php:const:: ORIG_MIGRATION_OPTION_NAME

        Name of the original database option storing the integer migration number.

    .. php:const:: VERSION_OPTION_NAME

        Name of the new database option storing the core software version number.

    .. php:method:: __construct(Omeka_Db $db, $migrationsDir)

        :type $db: Omeka_Db
        :param $db:
        :type $migrationsDir: string
        :param $migrationsDir:

    .. php:method:: setupTimestampMigrations()

        Set up Omeka to use timestamped database migrations.

        This creates the 'schema_migrations' table, drops the 'migration' option
        and adds the 'omeka_version' option to the database.

        :returns: void

    .. php:method:: markAllAsMigrated()

        Mark all of the migrations as having been run.  Used by the installer as
        a way of indicating that the database is entirely up to date.

        :returns: void

    .. php:method:: migrate($endTimestamp = null)

        Migrate the database schema.

        :type $endTimestamp: string
        :param $endTimestamp: (optional) Timestamp corresponding to the stop point for the migration.  If older than the current time, database will migrate down to that point.  If newer, the opposite.  Defaults to the current timestamp.
        :returns: void

    .. php:method:: canUpgrade()

        Determine whether or not it is possible to migrate the Omeka database up.

        This is based entirely on whether there exist any migrations that have not
        yet been applied.

        :returns: void

    .. php:method:: dbNeedsUpgrade()

        Determine whether the database must be upgraded.

        In order to return true, this requires that canUprade() == true, and also
        that Omeka's code has recently been upgraded.

    .. php:method:: finalizeDbUpgrade()

        Finalize the database upgrade by setting the most up-to-date version
        of Omeka.

    .. php:method:: getDefault($db = null)

        Return the default configuration of the database migration manager.

        :type $db: Omeka_Db|null
        :param $db:
        :returns: Omeka_Db_Migration_Manager

    .. php:method:: _getAllMigratedVersions()

        Retrieve all the versions that have been migrated.

        :returns: array

    .. php:method:: _getMigrationTableName()

        Return the name of the table associated with schema migrations.

        :returns: string

    .. php:method:: _getMigrationFileList()

        Return a list of migration files in the migration directory.

        :returns: array An associative array where key = timestamp of migration, value = full filename of the migration.

    .. php:method:: _migrateUp($stopAt)

        Migrate upwards to a specific timestamp.

        :type $stopAt: DateTime
        :param $stopAt:
        :returns: void

    .. php:method:: _loadMigration($filename)

        Require the migration file and return an instance of the class associated
        with it.

        :type $filename: string
        :param $filename: Migration script filename.
        :returns: Omeka_Db_Migration_AbstractMigration

    .. php:method:: _getPendingMigrations(DateTime $until)

        Retrieve a list of all migrations that have not been run yet, ending at
        the latest time given by $until.

        :type $until: DateTime
        :param $until:
        :returns: array

    .. php:method:: _recordMigration($time)

        Record the migration timestamp in the schema_migrations table.

        :type $time: string
        :param $time:
        :returns: void
