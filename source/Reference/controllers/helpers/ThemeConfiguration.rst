-------------------------------------------------
Omeka_Controller_Action_Helper_ThemeConfiguration
-------------------------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_ThemeConfiguration

extends :php:class:`Zend_Controller_Action_Helper_Abstract`

    Action helper for handling theme configuration.

    .. php:method:: processForm(Zend_Form $form, $data, $originalOptions = array())

        Process the theme configuration form.

        For file elements, this will save them using the storage system or remove
        them as is necessary.

        :type $form: Zend_Form
        :param $form: The form to save.
        :type $data: array
        :param $data: The data to fill the form with.
        :type $originalOptions: array
        :param $originalOptions: The previous options for the form.
        :returns: array|bool Array of options if the form was validly submitted, false otherwise.

    .. php:method:: _configFileElement(Zend_Form_Element_File $element)

        Ignore a file element that has an associated hidden element,
        since this means that the user did not change the uploaded file.

        :type $element: Zend_Form_Element_File
        :param $element:

    .. php:method:: _processFileElement(Zend_Form_Element_File $element)

        Store and/or delete a file for a file element.

        :type $element: Zend_Form_Element_File
        :param $element:

    .. php:method:: _deleteOldFile(Zend_Form_Element_File $element)

        Delete a previously-stored theme file.

        :type $element: Zend_Form_Element_File
        :param $element:
