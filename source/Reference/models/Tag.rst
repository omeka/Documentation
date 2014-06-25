---
Tag
---

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Tag

extends :php:class:`Omeka_Record_AbstractRecord`

    A tag and its metadata.

    .. php:attr:: name

        string

        The tag text.

    .. php:method:: __toString()

        Use the tag text when using this record as a string.

        :returns: string

    .. php:method:: _delete()

        Delete handling for a tag.

        Delete the taggings associated with this tag.

    .. php:method:: _validate()

        Validate this tag.

        The tag "name" must be non-empty and unique.

    .. php:method:: fieldIsUnique($field, $value = null)

        Check whether a field is unique.

        The check for unique tag names must take into account CASE SENSITIVITY,
        which is accomplished via COLLATE utf8_bin sql

        :param $field:
        :param $value:
        :returns: bool

    .. php:method:: rename($new_names)

        Rename a tag.

        Any records tagged with the "old" tag will be tagged with each of the tags
        given in $new_names. The original tag will be deleted (unless it is given
        as one of the $new_names).

        :type $new_names: array
        :param $new_names: Names of the tags this one should be renamed to.
