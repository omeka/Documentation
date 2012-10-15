----------------
Omeka_Form_Admin
----------------

.. php:class:: Omeka_Form_Admin

    A Zend_Form subclass to set up a record editing form for the Omeka 2.0 admin 
    user interface

    .. php:attr:: _editDisplayGroup
    


    .. php:attr:: _saveDisplayGroup
    


    .. php:attr:: _saveDisplayGroupActionDecorator
    


    .. php:attr:: _record
    


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

    .. php:method:: addElementToDisplayGroup($group, $element, $name, $options)
    
        :param unknown $group: 
        :param unknown $element: 
        :param unknown $name: 
        :param unknown $options:

    .. php:method:: getSaveGroupDefaultElementDecorators()

    .. php:method:: setEditGroupCssClass($cssClass)
    
        :param unknown $cssClass:

    .. php:method:: setSaveGroupCssClass($cssClass)
    
        :param unknown $cssClass:

    .. php:method:: setRecord($record)
    
        :param unknown $record:

    .. php:method:: setHasPublicPage($value = 1)
    
        :param unknown $value: