-------------------------
Omeka_Filter_HtmlPurifier
-------------------------

.. php:class:: Omeka_Filter_HtmlPurifier

    A Zend_Filter implementation that uses HtmlPurifier to purify a string

    .. php:attr:: _purifier
    


    .. php:attr:: _purifierConfig
    


    .. php:method:: filter($value)
    
        Filter the value
        
        :param unknown $value: 
        :returns: string An html purified string

    .. php:method:: getDefaultAllowedHtmlElements()
    
        Get the default allowed html elements.
        
        :returns: array An array of strings corresponding to the allowed html elements

    .. php:method:: getDefaultAllowedHtmlAttributes()
    
        Get the default allowed html attributes.
        
        :returns: array An array of strings corresponding to the allowed html attributes

    .. php:method:: getHtmlPurifier()
    
        Gets the html purifier singleton
        
        :returns: HTMLPurifier $purifier

    .. php:method:: setHtmlPurifier(HTMLPurifier $purifier)
    
        Sets the html purifier singleton
        
        :param HTMLPurifier $purifier: 
        :returns: void

    .. php:method:: createHtmlPurifier(array $allowedHtmlElements, array $allowedHtmlAttributes)
    
        :param array $allowedHtmlElements: An array of strings representing allowed HTML elements
        :param array $allowedHtmlAttributes: An array of strings representing allowed HTML attributes
        :returns: HTMLPurifier

    .. php:method:: filterAttributesWithMissingElements($htmlAttributes = Array, $htmlElements = Array)
    
        :param unknown $htmlAttributes: 
        :param unknown $htmlElements: