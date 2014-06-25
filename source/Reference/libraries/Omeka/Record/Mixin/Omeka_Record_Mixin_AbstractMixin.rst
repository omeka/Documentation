--------------------------------
Omeka_Record_Mixin_AbstractMixin
--------------------------------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Omeka_Record_Mixin_AbstractMixin

    Represents a kind of mixin for Omeka_Record_AbstractRecord implementations.

    Any methods declared for an implementation of this class can be called transparently by an Omeka_Record_AbstractRecord object that uses one of these modules.

    For instance, the Item model does not have an addTags() method, but the Taggable class does.  Since Item declares Taggable as one of its modules,
    an Item instance call all of Taggable's methods, so that adding tags would be as simple as calling $item->addTags('foo, bar');

    Note that this is not a true mixin because it cannot override any existing methods on a Record object.

    .. php:attr:: _record

        protected Omeka_Record_AbstractRecord

        Underlying record object.

    .. php:method:: __construct($record)

        Base mixin constructor.

        Store the underlying record for use in the mixin.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: beforeSave($args)

        Callback automatically called by Omeka_Record_AbstractRecord.

        See the corresponding {@link Omeka_Record_AbstractRecord} method for
        definitions of call times.

        :param $args:
        :returns: void

    .. php:method:: afterSave($args)

        :param $args:

    .. php:method:: beforeDelete()

    .. php:method:: afterDelete()
