------------
Mixin_Search
------------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_Search

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    Make an Omeka record fulltext searchable.

    Any class that extends Omeka_Record_AbstractRecord can be made searchable by pushing an instance of this mixin into Omeka_Record::$_mixins during Omeka_Record::_initializeMixins(). It must be pushed after all mixins that can add search text--for example, after ElementText.

    The record type must also be registered using the search_record_types filter in order for the records to be searchable.

    This mixin leverages the Omeka_Record_AbstractRecord::afterSave() and Omeka_Record_Mixin_AbstractMixin::afterSave() callbacks, so note their order of execution. Records that initialize ActsAsElementText will automatically add their element texts to the search text.

    .. php:attr:: _text

        protected

    .. php:attr:: _title

        protected

    .. php:attr:: _public

        protected

    .. php:method:: __construct($record)

        :param $record:

    .. php:method:: addSearchText($text)

        Add search text to this record.

        This method is meant to be called during afterSave().

        :type $text: string
        :param $text:

    .. php:method:: setSearchTextTitle($title)

        Add a title to this record.

        This method is meant to be called during afterSave().

        :type $title: string
        :param $title:

    .. php:method:: setSearchTextPrivate()

        Mark this record's search text as not public.

        This method is meant to be called during afterSave().

    .. php:method:: afterSave($args)

        Save the accumulated search text to the database.

        :param $args:

    .. php:method:: afterDelete()

        Delete this record's search text after it has been deleted.

    .. php:method:: saveSearchText($recordType, $recordId, $text, $title, $public = 1)

        Save a search text row.

        Call this statically only when necessary. Used primarily when in a record
        that does not implement Mixin_Search but contains text that is needed for
        another record's search text. For example, when saving a child record that
        contains search text that should be saved to its parent record.

        :type $recordType: string
        :param $recordType:
        :type $recordId: int
        :param $recordId:
        :type $text: string
        :param $text:
        :type $title: string
        :param $title:
        :type $public: int
        :param $public:
