--------------
TagsController
--------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: TagsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:attr:: _browseRecordsPerPage

        protected

    .. php:method:: init()

    .. php:method:: addAction()

    .. php:method:: editAction()

    .. php:method:: browseAction()

        Browse, filter and search tags

    .. php:method:: _getBrowseDefaultSort()

        Return the default sorting parameters to use when none are specified.

        :returns: array|null Array of parameters, with the first element being the  sort_field parameter, and the second (optionally) the sort_dir.

    .. php:method:: autocompleteAction()

    .. php:method:: renameAjaxAction()
