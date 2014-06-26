----------------------
Installer_Task_Options
----------------------

Package: :doc:`Install </Reference/packages/Install/index>`

.. php:class:: Installer_Task_Options

implements :php:interface:`Installer_TaskInterface`

    Installer task for inserting options into the options table.

    .. php:method:: setOptions($options)

        Set the key value pairs that will correspond to database options.

        :param $options:

    .. php:method:: install(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:
