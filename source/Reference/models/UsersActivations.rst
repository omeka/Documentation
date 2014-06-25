----------------
UsersActivations
----------------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: UsersActivations

extends :php:class:`Omeka_Record_AbstractRecord`

    An activation code for a User.

    .. php:attr:: user_id

        int

        The ID of the User this activation code is for.

    .. php:attr:: url

        string

        Random activation key.

    .. php:attr:: added

        string

        Date this activation key was created.

    .. php:attr:: _related

        protected array

        Related records.

    .. php:method:: factory(User $user)

        Get a new UsersActivations for a User.

        :type $user: User
        :param $user:
        :returns: UsersActivations

    .. php:method:: beforeSave($args)

        Before-save hook.

        Set the timestamp and create a random key.

        :param $args:

    .. php:method:: getUser()

        Get the User for this Activation.

        :returns: User
