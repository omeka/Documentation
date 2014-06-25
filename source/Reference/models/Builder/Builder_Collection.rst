------------------
Builder_Collection
------------------

Package: :doc:`Record\\Builder </Reference/packages/Record/Builder/index>`

.. php:class:: Builder_Collection

extends :php:class:`Omeka_Record_Builder_AbstractBuilder`

    Build a collection.

    .. php:attr:: _recordClass

        protected

    .. php:attr:: _settableProperties

        protected

    .. php:method:: setElementTexts($elementTexts)

        Set the element texts for the collection.

        :type $elementTexts: array
        :param $elementTexts:

    .. php:method:: _addElementTexts()

        Add element texts to a record.

    .. php:method:: _replaceElementTexts()

        Replace all the element texts for existing element texts.

    .. php:method:: _beforeBuild(Omeka_Record_AbstractRecord $record)

        Add elements associated with the collection.

        :type $record: Omeka_Record_AbstractRecord
        :param $record: The collection record
