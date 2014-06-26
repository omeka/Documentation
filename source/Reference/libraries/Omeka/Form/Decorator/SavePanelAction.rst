------------------------------------
Omeka_Form_Decorator_SavePanelAction
------------------------------------

Package: :doc:`Form\\Decorator </Reference/packages/Form/Decorator/index>`

.. php:class:: Omeka_Form_Decorator_SavePanelAction

extends :php:class:`Zend_Form_Decorator_Abstract`

    Decorator for buttons (usually actions) for the save panel in Omeka_Form_Admin

    .. php:attr:: content

        protected

    .. php:method:: getContent()

    .. php:method:: getRecord()

        Checks if a record was passed to the Omeka_Form_Admin form. returns it if
        it has been

        :returns: mixed false or the record

    .. php:method:: hasPublicPage()

        Checks if the Omeka_Form_Admin should display a link to a record's public
        page

    .. php:method:: render($content)

        Render html for the save panel buttons

        :type $content: string
        :param $content:
        :returns: string
