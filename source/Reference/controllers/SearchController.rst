----------------
SearchController
----------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: SearchController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:method:: init()

    .. php:method:: indexAction()

    .. php:method:: _getBrowseRecordsPerPage()

        Return the number of results to display per page.

        An authorized user can modify this using the "per_page" query parameter.

        :returns: int
