.. understandingformelements


###########################
Understanding Form Elements
###########################


Omeka makes heavy use of Zend's `Form_Element <http://framework.zend.com/manual/1.12/en/zend.form.elements.html>`_ class for building forms, rather than writing out the HTML explicitly.

Typically, elements are added directly to an :php:class:`Omeka_Form` object or an :php:class:`Omeka_Form_Admin` object.

The basic structure is to use the ``addElement()`` method, with three parameters:

``string`` $element
    A string name for the form element. Typical examples are: button, captcha, checkbox, file, multicheckbox, multiselect, radio, select, submit, text, textarea.
    
    An element object can also be passed in here. In this (rare) case, the other two parameters are usually unnecessary

``string`` $name
    The name attribute for the form element
    
``array`` $options
    Additional options for the form element. ``label``, ``description``, and ``required`` are the most common options. HTML attributes such as ``rows`` and ``cols`` can also appear here, as well as ``class``
    
    In more complex examples, an array of ``validators`` can also be passed here    

********
Examples
********

.. code-block:: php

        $form->addElement('textarea', 'description', array(
            'label' => __('Description'),
            'description' => __('My record description'),
            'rows' => 10
        ));
        
        $form->addElement('text', 'user_email', array(
            'label' => __('Email'),
            'description' => __("Prefered email address of the person submitting the record"),
            'validators' => array('EmailAddress'), 
            'required' => true
        ));


For a more extended example, see the IndexController::_getForm() method in the SimplePages plugin, bundled with Omeka.

********
See Also
********

:php:class:`Omeka_Form`
:php:class:`Omeka_Form_Admin`
:ref:`understandingomekaformadmin`