---------------------
CollectionsController
---------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: CollectionsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:attr:: _autoCsrfProtection

        protected

    .. php:attr:: contexts

    .. php:attr:: _browseRecordsPerPage

        protected

    .. php:method:: init()

    .. php:method:: showAction()

        The show collection action

    .. php:method:: addAction()

        The add collection action

    .. php:method:: editAction()

        The edit collection action

    .. php:method:: _getAddSuccessMessage($collection)

        :param $collection:

    .. php:method:: _getEditSuccessMessage($collection)

        :param $collection:

    .. php:method:: _getDeleteSuccessMessage($collection)

        :param $collection:

    .. php:method:: _getDeleteConfirmMessage($collection)

        :param $collection:

    .. php:method:: _getElementMetadata($collection, $elementSetName, $elementName)

        :param $collection:
        :param $elementSetName:
        :param $elementName:

    .. php:method:: _getCollectionElementSets()

        Gets the element sets for the 'Collection' record type.

        :returns: array The element sets for the 'Collection' record type

    .. php:method:: _getBrowseDefaultSort()
