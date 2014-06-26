---------
Mixin_Tag
---------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_Tag

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    .. php:method:: __construct(Omeka_Record_AbstractRecord $record)

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: beforeDelete()

        Fires whenever deleting a record that is taggable
        This will actually delete all the references to a specific tag for a
        specific record

        :returns: void

    .. php:method:: afterSave($args)

        :param $args:

    .. php:method:: deleteTaggings()

    .. php:method:: getTaggings()

        Retrieve all the Taggings objects that represent between a specific tag
        and the current record
        Called by whatever record has enabled this module

        :returns: array of Taggings

    .. php:method:: getTags($order = array())

        Get all the Tag records associated with this record

        :param $order:
        :returns: array of Tag

    .. php:method:: deleteTags($tags, $delimiter = null)

        Delete a tag from the record

        :type $tags: string|array
        :param $tags: The tag name or array of tag names to delete from the record
        :type $delimiter: string
        :param $delimiter: The delimiter of the tags. Not applicable if $tags is an array
        :returns: bool Returns whether a tag in $tags was deleted. Returns false if $tags is empty. Returns true if at least one tag in $tags is deleted.

    .. php:method:: hasTag($tag)

        If the $tag were a string and the keys of Tags were just the names of the
        tags, this would be:
        in_array(array_keys($this->Tags))

        :param $tag:
        :returns: boolean

    .. php:method:: _getTagsFromString($string, $delimiter = null)

        Converts a delimited string of tags into an array of tag strings

        :type $string: string
        :param $string: A delimited string of tags
        :param $delimiter:
        :returns: array An array of tag strings

    .. php:method:: addTags($tags, $delimiter = null)

        Set tags to be saved to the record.

        :type $tags: array|string
        :param $tags: Either an array of tags or a delimited string
        :param $delimiter:
        :returns: void

    .. php:method:: applyTags($inputTags)

        Apply tags

        :type $inputTags: array
        :param $inputTags:

    .. php:method:: diffTags($inputTags, $tags = null)

        Calculate the difference between a tag string and a set of tags

        :param $inputTags:
        :param $tags:
        :returns: array Keys('removed','added')

    .. php:method:: applyTagString($string, $delimiter = null)

        This will add tags that are in the tag string and remove those that are
        no longer in the tag string

        :type $string: string
        :param $string: A string of tags delimited by $delimiter
        :type $delimiter: string|null
        :param $delimiter:
