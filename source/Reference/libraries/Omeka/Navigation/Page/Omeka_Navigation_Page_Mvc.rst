-------------------------
Omeka_Navigation_Page_Mvc
-------------------------

Package: :doc:`Navigation </Reference/packages/Navigation/index>`

.. php:class:: Omeka_Navigation_Page_Mvc

extends :php:class:`Zend_Navigation_Page_Mvc`

    Customized subclass of Zend Framework's Zend_Navigation_Page_Mvc class.

    .. php:attr:: _theme

        protected string

        Theme option to use when assembling URL

    .. php:method:: getHref()

        Returns href for this page

        This method uses {@link Zend_Controller_Action_Helper_Url} to assemble the
        href based on the page's properties.

        :returns: string  page href

    .. php:method:: getTheme()

        Returns theme option to use when assembling URL

        :returns: string|null  theme option

    .. php:method:: setTheme($theme)

        Sets theme option to use when assembling URL

        :param $theme:
        :returns: Omeka_Navigation_Page_Mvc   fluent interface, returns self
