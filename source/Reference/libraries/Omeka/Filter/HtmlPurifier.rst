-------------------------
Omeka_Filter_HtmlPurifier
-------------------------

Package: :doc:`Filter </Reference/packages/Filter/index>`

.. php:class:: Omeka_Filter_HtmlPurifier

implements :php:interface:`Zend_Filter_Interface`

    A Zend_Filter implementation that uses HtmlPurifier to purify a string.

    .. php:method:: filter($value)

        Filter the value

        :param $value:
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

    .. php:method:: setHtmlPurifier($purifier)

        Sets the html purifier singleton

        :type $purifier: HTMLPurifier
        :param $purifier:

    .. php:method:: createHtmlPurifier($allowedHtmlElements = null, $allowedHtmlAttributes = null)

        :type $allowedHtmlElements: array
        :param $allowedHtmlElements: An array of strings representing allowed HTML elements
        :type $allowedHtmlAttributes: array
        :param $allowedHtmlAttributes: An array of strings representing allowed HTML attributes
        :returns: HTMLPurifier

    .. php:method:: filterAttributesWithMissingElements($htmlAttributes = array(), $htmlElements = array())

        :param $htmlAttributes:
        :param $htmlElements:
