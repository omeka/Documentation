------------------------------------
Omeka_Controller_Plugin_HtmlPurifier
------------------------------------

.. php:class:: Omeka_Controller_Plugin_HtmlPurifier

    Package: Controller\Plugin

    This ZF controller plugin allows the HtmlPurifier to filter the existing 
    forms (items, collections, users, etc.) so that fields that are allowed to 
    contain HTML are properly filtered.
    
    Note that this will not operate on any of the plugins.

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)
    
        Add the HtmlPurifier options if needed.
        
        :param Zend_Controller_Request_Abstract $request: 
        :returns: void

    .. php:method:: preDispatch(Zend_Controller_Request_Abstract $request)
    
        Determine whether or not to filter form submissions for various controllers.
        
        :param Zend_Controller_Request_Abstract $request: 
        :returns: void

    .. php:method:: isFormSubmission(Zend_Controller_Request_Abstract $request)
    
        Determine whether or not the request contains a form submission to either
        the 'add', 'edit', or 'config' actions.
        
        :param Zend_Controller_Request_Abstract $request: 
        :returns: boolean

    .. php:method:: filterCollectionsForm(Zend_Controller_Request_Abstract $request, Omeka_Filter_HtmlPurifier $htmlPurifierFilter)
    
        Title = Plain text.
        Description = HTML.
        
        :param Zend_Controller_Request_Abstract $request: 
        :param Omeka_Filter_HtmlPurifier $htmlPurifierFilter: 
        :returns: void

    .. php:method:: filterThemesForm(Zend_Controller_Request_Abstract $request, Omeka_Filter_HtmlPurifier $htmlPurifierFilter)
    
        Purify all of the data in the theme settings
        
        :param Zend_Controller_Request_Abstract $request: 
        :param Omeka_Filter_HtmlPurifier $htmlPurifierFilter: 
        :returns: void

    .. php:method:: _purifyArray($dataArray = Array, Omeka_Filter_HtmlPurifier $htmlPurifierFilter)
    
        Recurisvely purify an array
        
        :param unknown $dataArray: 
        :param Omeka_Filter_HtmlPurifier $htmlPurifierFilter: 
        :returns: array A purified array of string or array values

    .. php:method:: filterItemsForm(Zend_Controller_Request_Abstract $request, Omeka_Filter_HtmlPurifier $htmlPurifierFilter)
    
        Filter the 'Elements' array of the POST.
        
        :param Zend_Controller_Request_Abstract $request: 
        :param Omeka_Filter_HtmlPurifier $htmlPurifierFilter: 
        :returns: void

    .. php:method:: _setupHtmlPurifierOptions()