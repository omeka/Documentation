----------------
Omeka_Form_Admin
----------------

.. php:class:: Omeka_Form_Admin

    Package: :doc:`Form </Reference/packages/Form/index>`

    A Zend_Form subclass to set up a record editing form for the Omeka 2.0 admin 
    user interface

    .. php:attr:: _editDisplayGroup
    


    .. php:attr:: _saveDisplayGroup
    


    .. php:attr:: _saveDisplayGroupActionDecorator
    


    .. php:attr:: _record
    


    .. php:attr:: _type
    


    .. php:attr:: _hasPublicPage
    


    .. php:attr:: _editGroupCssClass
    


    .. php:attr:: _saveGroupCssClass
    


    .. php:method:: init()

    .. php:method:: addElementToEditGroup(Zend_Form_Element|string $element, string|null $name, array|null $options)
    
        Add an element to the edit area
        
        :param Zend_Form_Element|string $element: 
        :param string|null $name: 
        :param array|null $options:

    .. php:method:: addElementToSaveGroup(Zend_Form_Element|string $element, string|null $name, array|null $options)
    
        Add an element to the save panel
        
        :param Zend_Form_Element|string $element: 
        :param string|null $name: 
        :param array|null $options:

    .. php:method:: addElementToDisplayGroup(string $group, Zend_Form_Element $element, string $name, array $options)
    
        Generalizes creating and adding new elements to one of the display groups
        
        You can pass in either an Zend_Form_Element you have already created, or passparameters as you would to Zend_Form::addElement
        
        :param string $group: Either 'save' or 'edit'
        :param Zend_Form_Element $element: The element to add to the display group
        :param string $name: 
        :param array $options: 
        :returns: Omeka_Form_Admin

    .. php:method:: getSaveGroupDefaultElementDecorators()
    
        Get the decorators for the save display group
        
        :returns: array The default decorators for the save display group

    .. php:method:: setEditGroupCssClass(string $cssClass)
    
        Set the class for the edit display group.
        
        You can alter the default css class for the edit group panel by passing in anoption for 'editGroupCssClass' when you create an instance of Omeka_Form_Admin.This should be done very sparingly, as the default class is the best match toexisting admin theme look and feel
        
        :param string $cssClass:

    .. php:method:: setSaveGroupCssClass(string $cssClass)
    
        Set the class for the save display group.
        
        You can alter the default css class for the save group panel by passing in anoption for 'editGroupCssClass' when you create an instance of Omeka_Form_Admin.This should be done very sparingly, as the default class is the best match toexisting admin theme look and feel
        
        :param string $cssClass:

    .. php:method:: setType(string $type)
    
        Set the record type of the object being edited (e.g., 'item')
        
        Pass in the recordType as part of the options array when you create an instance
        
        :param string $type:

    .. php:method:: setRecord(Omeka_Record_AbstractRecord $record)
    
        Set the record (if one exists) for the object being edited
        
        Passing the record object as part of the options when you create the formwill automatically add 'Edit' and 'Delete' buttons to the save panel
        
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: setHasPublicPage(bool $value = )
    
        Set whether the save panel should display a link to the record's public page if it exists
        
        By default, a link to a record's public page is available if it exists. Pass false as the value of hasPublicPage in the options array to suppress this behavior.
        
        :param bool $value: true