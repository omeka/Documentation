----------------------------------
Omeka_Application_Resource_Session
----------------------------------

Package: :doc:`Application\\Resource </Reference/packages/Application/Resource/index>`

.. php:class:: Omeka_Application_Resource_Session

extends :php:class:`Zend_Application_Resource_Session`

    Initialize the session.

    Customizes the session name to prevent session overlap between different applications that operate on the same server.

    .. php:method:: init()

    .. php:method:: _getSessionConfig()

        Retrieve global session configuration options.

        :returns: array An array containing all the global configuration options for sessions.  This array contains at least one key, 'name', corresponding to the name of the session, which is generated automatically if not provided.

    .. php:method:: _buildSessionName()

        Create a unique session name.

        Hashes the base directory, this ensures that session names differ between
        Omeka instances on the same server.

        :returns: string

    .. php:method:: _setOptionsFromConfig()

    .. php:method:: _canUseDbSessions($options)

        Check if the DB is recent enough to use DB sessions by default.

        Recent enough means that the DB version is 2.0 or higher. We can't use the
        DB sessions until the upgrade is complete to 2.0+.

        :type $options: array
        :param $options:
        :returns: bool
