--------------------
Mixin_PublicFeatured
--------------------

Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

.. php:class:: Mixin_PublicFeatured

extends :php:class:`Omeka_Record_Mixin_AbstractMixin`

    Adds default behavior associated with the 'public' and 'featured' flags.

    .. php:method:: __construct($record)

        Constructor

        :type $record: Omeka_Record_AbstractRecord
        :param $record: The underlying record

    .. php:method:: isPublic()

        Returns whether the record is public or not.

        :returns: boolean

    .. php:method:: setPublic($flag)

        Sets whether the record is public or not.

        :type $flag: boolean
        :param $flag: Whether the record is public or not

    .. php:method:: isFeatured()

        Returns whether the record is featured or not.

        :returns: boolean

    .. php:method:: setFeatured($flag)

        Sets whether the record is featured or not.

        :type $flag: boolean
        :param $flag: Whether the record is featured or not

    .. php:method:: beforeSave($args)

        :param $args:

    .. php:method:: afterSave($args)

        :param $args:

    .. php:method:: _fireHook($state, $flag)

        Fires a hooks like 'make_item_public', 'make_collection_not_featured',
        etc.

        :type $state: string
        :param $state: Currently, 'public' or 'featured'
        :type $flag: boolean
        :param $flag:

    .. php:method:: _getHookName($state, $flag)

        Retrieve formatted hooks like 'make_item_public',
        'make_collection_not_featured', etc.

        :type $state: string
        :param $state: Currently, 'public' or 'featured'
        :type $flag: boolean
        :param $flag:
        :returns: string The hook name
