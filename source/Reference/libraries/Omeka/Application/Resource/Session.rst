----------------------------------
Omeka_Application_Resource_Session
----------------------------------

.. php:class:: Omeka_Application_Resource_Session

    Package: :doc:`/Reference/packages/Application\Resource/index`

    Initialize the session.
    
    Customizes the session name to prevent session overlap between differentapplications that operate on the same server.

    .. php:method:: init()

    .. php:method:: _getSessionConfig()
    
        Retrieve global session configuration options.
        
        :returns: array An array containing all the global configuration options for sessions.  This array contains at least one key, 'name', corresponding to the name of the session, which is generated automatically if not provided.

    .. php:method:: _buildSessionName()
    
        Create a unique session name.
        
        Hashes the base directory, this ensures that session names differ betweenOmeka instances on the same server.
        
        :returns: string

    .. php:method:: _setOptionsFromConfig()