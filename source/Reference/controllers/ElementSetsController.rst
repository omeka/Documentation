---------------------
ElementSetsController
---------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: ElementSetsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:method:: init()

    .. php:method:: _getDeleteConfirmMessage($record)

        :param $record:

    .. php:method:: addAction()

        Can't add element sets via the admin interface, so disable these
        actions from being POST'ed to.

    .. php:method:: editAction()

    .. php:method:: _redirectAfterEdit($record)

        :param $record:
