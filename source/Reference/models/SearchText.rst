----------
SearchText
----------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: SearchText

extends :php:class:`Omeka_Record_AbstractRecord`

    An entry in the site-wide fulltext search index for a record.

    .. php:attr:: record_type

        int

        Type of this text's associated record.

    .. php:attr:: record_id

        int

        ID of this text's associated record.

    .. php:attr:: public

        int

        Whether this text is publicly accessible.

    .. php:attr:: title

        string

        Display title for the record in search results.

    .. php:attr:: text

        string

        Searchable text for the record.
