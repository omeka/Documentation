---------------
ItemsController
---------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: ItemsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:attr:: _autoCsrfProtection

        protected

    .. php:attr:: _browseRecordsPerPage

        protected

    .. php:attr:: contexts

    .. php:method:: init()

    .. php:method:: preDispatch()

    .. php:method:: searchAction()

        This shows the search form for items by going to the correct URI.

        This form can be loaded as a partial by calling items_search_form().

        :returns: void

    .. php:method:: _getItemElementSets()

        Gets the element sets for the 'Item' record type.

        :returns: array The element sets for the 'Item' record type

    .. php:method:: editAction()

        Adds an additional permissions check to the built-in edit action.

    .. php:method:: _getAddSuccessMessage($item)

        :param $item:

    .. php:method:: _getEditSuccessMessage($item)

        :param $item:

    .. php:method:: _getDeleteSuccessMessage($item)

        :param $item:

    .. php:method:: _getDeleteConfirmMessage($item)

        :param $item:

    .. php:method:: _getElementMetadata($item, $elementSetName, $elementName)

        :param $item:
        :param $elementSetName:
        :param $elementName:

    .. php:method:: addAction()

    .. php:method:: tagsAction()

        Finds all tags associated with items (used for tag cloud)

        :returns: void

    .. php:method:: browseAction()

        Browse the items.  Encompasses search, pagination, and filtering of
        request parameters.  Should perhaps be split into a separate
        mechanism.

        :returns: void

    .. php:method:: _getBrowseDefaultSort()

    .. php:method:: changeTypeAction()

        Find or create an item for this mini-form

    .. php:method:: batchEditAction()

        Batch editing of Items. If this is an AJAX request, it will
        render the 'batch-edit' as a partial.

        :returns: void

    .. php:method:: batchEditSaveAction()

        Processes batch edit information. Only accessible via POST.

        :returns: void

    .. php:method:: _batchEditAllSave()

        Processes batch edit all information. Only accessible via POST.

        :returns: void
