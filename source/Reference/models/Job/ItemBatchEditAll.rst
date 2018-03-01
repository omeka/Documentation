--------------------
Job_ItemBatchEditAll
--------------------

Package: :doc:`Job </Reference/packages/Job/index>`

.. php:class:: Job_ItemBatchEditAll

extends :php:class:`Omeka_Job_AbstractJob`

    .. php:attr:: _table

        protected

    .. php:attr:: _aclHelper

        protected

    .. php:method:: perform()

    .. php:method:: _performItem($itemId)

        Check if the item can be processed, then process it if possible.

        :type $itemId: int
        :param $itemId:
        :returns: bool

    .. php:method:: _logProcessedItem($message, $priority)

        Log a message about the current processed item.

        :type $message: string
        :param $message:
        :type $priority: string
        :param $priority:
