----------------
Omeka_Form_Admin
----------------

Package: :doc:`Form </Reference/packages/Form/index>`

.. php:class:: Omeka_Form_Admin

extends :php:class:`Omeka_Form`

    A Zend_Form subclass to set up a record editing form for the Omeka 2.0 admin
    user interface

    .. php:attr:: _editDisplayGroup

        protected

    .. php:attr:: _saveDisplayGroup

        protected

    .. php:attr:: _saveDisplayGroupActionDecorator

        protected

    .. php:attr:: _record

        protected

    .. php:attr:: _type

        protected

    .. php:attr:: _hasPublicPage

        protected

    .. php:attr:: _editGroupCssClass

        protected

    .. php:attr:: _saveGroupCssClass

        protected

    .. php:method:: init()

    .. php:method:: addElementToEditGroup($element, $name, $options = null)

        Add an element to the edit area

        :type $element: Zend_Form_Element|string
        :param $element:
        :type $name: string|null
        :param $name:
        :type $options: array|null
        :param $options:

    .. php:method:: addElementToSaveGroup($element, $name = null, $options = null)

        Add an element to the save panel

        :type $element: Zend_Form_Element|string
        :param $element:
        :type $name: string|null
        :param $name:
        :type $options: array|null
        :param $options:

    .. php:method:: addElementToDisplayGroup($group, $element, $name = null, $options = null)

        Generalizes creating and adding new elements to one of the display groups

        You can pass in either an Zend_Form_Element you have already created, or
        pass parameters as you would to Zend_Form::addElement

        :type $group: string
        :param $group: Either 'save' or 'edit'
        :type $element: Zend_Form_Element
        :param $element: The element to add to the display group
        :type $name: string
        :param $name:
        :type $options: array
        :param $options:
        :returns: Omeka_Form_Admin

    .. php:method:: getSaveGroupDefaultElementDecorators()

        Get the decorators for the save display group

        :returns: array The default decorators for the save display group

    .. php:method:: setEditGroupCssClass($cssClass)

        Set the class for the edit display group.

        You can alter the default css class for the edit group panel by passing in
        an option for 'editGroupCssClass' when you create an instance of
        Omeka_Form_Admin.
        This should be done very sparingly, as the default class is the best match
        to existing admin theme look and feel

        :type $cssClass: string
        :param $cssClass:

    .. php:method:: setSaveGroupCssClass($cssClass)

        Set the class for the save display group.

        You can alter the default css class for the save group panel by passing in
        an option for 'editGroupCssClass' when you create an instance of
        Omeka_Form_Admin.
        This should be done very sparingly, as the default class is the best match
        to existing admin theme look and feel

        :type $cssClass: string
        :param $cssClass:

    .. php:method:: setType($type)

        Set the record type of the object being edited (e.g., 'item')

        Pass in the recordType as part of the options array when you create an
        instance

        :type $type: string
        :param $type:

    .. php:method:: setRecord($record)

        Set the record (if one exists) for the object being edited

        Passing the record object as part of the options when you create the form
        will automatically add 'Edit' and 'Delete' buttons to the save panel

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: setHasPublicPage($value = false)

        Set whether the save panel should display a link to the record's public
        page if it exists

        By default, a link to a record's public page is available if it exists.
        Pass false as the value of hasPublicPage in the options array to suppress
        this behavior.

        :type $value: bool
        :param $value: true
