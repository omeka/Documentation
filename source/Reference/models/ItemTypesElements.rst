-----------------
ItemTypesElements
-----------------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: ItemTypesElements

extends :php:class:`Omeka_Record_AbstractRecord`

    Record linking an Element with an ItemType.

    .. php:attr:: item_type_id

        int

        ID for the ItemType being linked.

    .. php:attr:: element_id

        int

        ID for the Element being linked.

    .. php:attr:: order

        int

        Relative order of the Element within the ItemType.
