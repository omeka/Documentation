------------------
Builder_ElementSet
------------------

Package: :doc:`Record\\Builder </Reference/packages/Record/Builder/index>`

.. php:class:: Builder_ElementSet

extends :php:class:`Omeka_Record_Builder_AbstractBuilder`

    Build an element set.

    .. php:attr:: _settableProperties

        protected

    .. php:attr:: _recordClass

        protected

    .. php:method:: setElements($elements)

        Set the elements to add to the element set.

        :type $elements: array
        :param $elements:

    .. php:method:: setRecordMetadata($metadata)

        Overrides setRecordMetadata() to allow giving the name of the element as
        a string.

        :type $metadata: string|array
        :param $metadata:

    .. php:method:: _beforeBuild()

        Add elements to be associated with the element set.
