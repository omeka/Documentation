----------------------------------
Omeka_Application_Resource_Options
----------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Options

extends :php:class:`Zend_Application_Resource_ResourceAbstract`

    Retrieve all the options from the database.

    Options are essentially site-wide variables that are stored in the database,
    for example the title of the site. Failure to load this resource currently indicates that Omeka needs to be installed.

    .. php:method:: init()

        :returns: array

    .. php:method:: setInstallerRedirect($flag)

        :param $flag:

    .. php:method:: _convertMigrationSchema($options)

        If necessary, convert from the old sequentially-numbered migration scheme
        to the new timestamped migrations.

        :param $options:
        :returns: void.
