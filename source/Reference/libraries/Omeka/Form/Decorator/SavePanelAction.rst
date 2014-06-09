------------------------------------
Omeka_Form_Decorator_SavePanelAction
------------------------------------

.. php:class:: Omeka_Form_Decorator_SavePanelAction

    Package: :doc:`Form\\Decorator </Reference/packages/Form/Decorator/index>`

    Decorator for buttons (usually actions) for the save panel in Omeka_Form_Admin

    .. php:attr:: content
    


    .. php:method:: getContent()

    .. php:method:: getRecord()
    
        Checks if a record was passed to the Omeka_Form_Admin form. returns it if it has been
        
        :returns: mixed false or the record

    .. php:method:: hasPublicPage()
    
        Checks if the Omeka_Form_Admin should display a link to a record's public page

    .. php:method:: render(string $content)
    
        Render html for the save panel buttons
        
        :param string $content: 
        :returns: string