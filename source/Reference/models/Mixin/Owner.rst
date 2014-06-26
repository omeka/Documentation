-----------
Mixin_Owner
-----------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_Owner

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    Mixin for models that have a user that is their "owner."

    .. php:attr:: _record

        protected

    .. php:attr:: _column

        protected

    .. php:method:: __construct($record, $column = 'owner_id')

        :param $record:
        :param $column:

    .. php:method:: beforeSave($args)

        :param $args:

    .. php:method:: setOwner(User $user)

        Set the record's owner.

        :type $user: User
        :param $user:

    .. php:method:: getOwner()

        Get the record's owner.

        If the record has no user, this method returns null.

        :returns: User|null

    .. php:method:: isOwnedBy(User $user)

        Check if the given User owns this record.

        :type $user: User
        :param $user:
        :returns: boolean
