----------------------------------
Omeka_Application_Resource_Options
----------------------------------

.. php:class:: Omeka_Application_Resource_Options

    Package: Application\Resource

    Retrieve all the options from the database.
    
    Options are essentially site-wide variables that are stored in the database,for example the title of the site. Failure to load this resource currentlyindicates that Omeka needs to be installed.

    .. php:attr:: _installerRedirect
    


    .. php:method:: init()
    
        :returns: array

    .. php:method:: setInstallerRedirect($flag)
    
        :param unknown $flag:

    .. php:method:: _convertMigrationSchema($options)
    
        If necessary, convert from the old sequentially-numbered migration scheme
        to the new timestamped migrations.
        
        :param unknown $options: 
        :returns: void.