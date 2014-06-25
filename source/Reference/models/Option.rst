------
Option
------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Option

extends :php:class:`Omeka_Record_AbstractRecord`

    A site option saved in the database.

    Options are stored and accessed by string keys.

    .. php:attr:: name

        string

        Option name.

    .. php:attr:: value

        string

        Option value.

    .. php:method:: __toString()

        Use the option's value when treating it as a string.

        :returns: string

    .. php:method:: _validate()

        Validate the Option.

        An option must have a non-empty and unique name.
