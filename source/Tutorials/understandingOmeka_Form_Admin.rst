.. _understandingomekaformadmin

##############################
Understanding Omeka_Form_Admin
##############################

:php:class:`Omeka_Form_Admin` is designed to make it easier for most plugins to conform to the look and feel of Omeka's admin interface. In most, but not all, cases, this class will let you easily construct your form. More complex forms might require building the form from scratch.

Like the rest of Omeka, it relies heavily on Zend's form elements. Read :ref:`understandingformelements` for a primer.


******
Basics
******

The admin editing screen generally consist of two areas, the 'main' area and the 'save panel', which includes the save and delete buttons, as well as miscellaneous buttons and sometimes some form elements. Omeka_Form_Admin is meant to make building those areas in a way that keeps the look and feel as the rest of the admin theme as easy as possible for most kinds of forms. It does this by creating a DisplayGroup for each of the two areas, styling them appropriately, and letting you add your form elements to them.

It is generally best to put the logic for building your form inside a method of your controller, e.g. in ``_getForm($record)``. You then add it to your add and edit views the usual way: ``$this->view->form = $this->_getForm($record)``. Generally, extending Omeka_Form_Admin is not necessary.

Create the form like so:

.. code-block:: php

    protected function _getForm($record)
    {

        $formOptions = array('type' => 'my_type', 'hasPublicPage'=>true);
        if($record && $record->exists()) {
            $formOptions['record'] = $record;
        }
        
        $form = new Omeka_Form_Admin($formOptions);
        
        // build the form elements
        
        return $form;
    }

The form option ``type`` is required. Typically, this is the name of your record type (e.g., 'item'). Hooks into the save panel are based on this type. See :ref:`admintypepanelbuttons`, :ref:`admintypepanelfields`, and :ref:`admintypeform`

``hasPublicPage`` is a flag to determine whether a link to the record's public page should be created in the save panel. Defaults to false.


***************************
Building the main edit area
***************************

The 'main' content area is where the primary parts of your form go: text inputs, most select dropdowns, etc.

Use the :php:meth:`Omeka_Form_Admin::addElementToEditGroup` to add your elements to the main edit area:

.. code-block: php

        $form->addElementToEditGroup('text',
                        'title',
                        array('id'=>'my_plugin_title',
                                'size'  => 40,
                                'value' => metadata($record, 'title'),
                                'label' => 'Title',
                                'description' => 'The title of the page (required).',
                                'required' => true
                        ));


***********************
Building the save panel
***********************

The save and delete buttons will the automatically added to the save panel. Some true form elements also make more sense in this area than in the main editing area. Often, data that is entered via a simple checkbox is a good candidate for having the form element here. Whether a page is public or not is a good example.

.. code-block:: php

        $form->addElementToSaveGroup('checkbox', 'is_published',
                        array('id' => 'my_plugin_is_published',
                                'values' => array(1, 0),
                                'checked' => metadata($record, 'is_published'),
                                'label' => 'Publish this page?',
                                'description' => 'Checking this box will make the page public.'
                        ));

