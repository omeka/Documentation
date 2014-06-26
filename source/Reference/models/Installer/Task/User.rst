-------------------
Installer_Task_User
-------------------

Package: :doc:`Install\\Task </Reference/packages/Install/Task/index>`

.. php:class:: Installer_Task_User

implements :php:interface:`Installer_TaskInterface`

    Create a default user for an Omeka installation.

    .. php:method:: setUsername($username)

        :param $username:

    .. php:method:: setPassword($password)

        :param $password:

    .. php:method:: setEmail($email)

        :param $email:

    .. php:method:: setName($name)

        :param $name:

    .. php:method:: setIsActive($active)

        :param $active:

    .. php:method:: setRole($role)

        :param $role:

    .. php:method:: install(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:
