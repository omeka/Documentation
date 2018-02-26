------------------------------------
Omeka_Controller_Plugin_HtmlPurifier
------------------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_HtmlPurifier

extends :php:class:`Zend_Controller_Plugin_Abstract`

    This ZF controller plugin allows the HtmlPurifier to filter the existing
    forms (items, collections, users, etc.) so that fields that are allowed to
    contain HTML are properly filtered.

    Note that this will not operate on any of the plugins.

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)

        Add the HtmlPurifier options if needed.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)

        Determine whether or not to filter form submissions for various
        controllers.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:

    .. php:method:: isFormSubmission($request)

        Determine whether or not the request contains a form submission to either
        the 'add', 'edit', or 'config' actions.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :returns: bool

    .. php:method:: filterCollectionsForm($request, $htmlPurifierFilter = null)

        Filter the Collections form post, including the 'Elements' array of the
        POST.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :type $htmlPurifierFilter: Omeka_Filter_HtmlPurifier
        :param $htmlPurifierFilter:

    .. php:method:: filterThemesForm($request, $htmlPurifierFilter = null)

        Purify all of the data in the theme settings

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :type $htmlPurifierFilter: Omeka_Filter_HtmlPurifier
        :param $htmlPurifierFilter:

    .. php:method:: _purifyArray($dataArray = array(), $htmlPurifierFilter = null)

        Recurisvely purify an array

        :param $dataArray:
        :type $htmlPurifierFilter: Omeka_Filter_HtmlPurifier
        :param $htmlPurifierFilter:
        :returns: array A purified array of string or array values

    .. php:method:: filterItemsForm($request, $htmlPurifierFilter = null)

        Filter the Items form post, including the 'Elements' array of the POST.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:
        :type $htmlPurifierFilter: Omeka_Filter_HtmlPurifier
        :param $htmlPurifierFilter:

    .. php:method:: _filterElementsFromPost($post, $htmlPurifierFilter = null)

        Filter the 'Elements' array of the POST.

        :type $post: Zend_Controller_Request_Abstract
        :param $post:
        :type $htmlPurifierFilter: Omeka_Filter_HtmlPurifier
        :param $htmlPurifierFilter:

    .. php:method:: _setupHtmlPurifierOptions()
