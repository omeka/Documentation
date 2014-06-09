-------------------------------------------------
Omeka_Controller_Action_Helper_ThemeConfiguration
-------------------------------------------------

.. php:class:: Omeka_Controller_Action_Helper_ThemeConfiguration

    Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

    Action helper for handling theme configuration.

    .. php:attr:: _themeOptions
    


    .. php:attr:: _formValues
    


    .. php:attr:: _form
    


    .. php:method:: processForm(Zend_Form $form, array $data, array $originalOptions)
    
        Process the theme configuration form.
        
        For file elements, this will save them using the storage systemor remove them as is necessary.
        
        :param Zend_Form $form: The form to save.
        :param array $data: The data to fill the form with.
        :param array $originalOptions: The previous options for the form.
        :returns: array|bool Array of options if the form was validly submitted, false otherwise.

    .. php:method:: _configFileElement(Zend_Form_Element_File $element)
    
        Ignore a file element that has an associated hidden element,
        since this means that the user did not change the uploaded file.
        
        :param Zend_Form_Element_File $element:

    .. php:method:: _processFileElement(Zend_Form_Element_File $element)
    
        Store and/or delete a file for a file element.
        
        :param Zend_Form_Element_File $element:

    .. php:method:: _deleteOldFile(Zend_Form_Element_File $element)
    
        Delete a previously-stored theme file.
        
        :param Zend_Form_Element_File $element: