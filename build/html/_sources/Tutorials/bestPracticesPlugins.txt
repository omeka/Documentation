.. bestPracticesPlugins.


#####################################
Best Practices for Plugin Development
#####################################



*************************
Method Naming Conventions
*************************

Method names must be in camelCase (e.g., ``getItem()``).

For private or protected methods, prefix the method name with underscore (_).

See also `Zend's Coding Standards <http://framework.zend.com/wiki/display/ZFDEV2/Coding+Standards#CodingStandards-FunctionsandMethods>`_

************************************
Maintain expected behaviors in Omeka
************************************

Omeka defines some hooks that operate on every record. For example, Omeka's :php:meth:`Omeka_Record_AbstractRecord::save` method fires hooks before and after saving. In most cases, you don't need to override it, but if you do, make sure you include ``$this->runCallbacks('beforeSave', $callbackArgs);`` and ``$this->runCallbacks('afterSave', $callbackArgs);`` where appropriate.

Similarly, whenever you override methods from abstract classes in Omeka, make sure that you have studied the parent methods' code to include all the expected callback. This will allow other developers to work with the expected behaviors of the objects.

Also, if you use any non-standard routing in your plugin, you must override :php:meth:`Omeka_Record_AbstractRecord::getRecordUrl` so that it returns the correct url to the record. Compare the ``getRecordUrl()`` method on the ``SimplePagesPage`` model in the "Simple Pages" plugin.



***************** 
Use View Partials
*****************

View partials let you separate out parts of long or complicated views into separate files. For example, if you have a browse view that allows different ordering, it is best to use view partials to separate the code for the different orderings to be in different partials. For example:

.. code-block:: php

    <?php if (isset($_GET['view']) && $_GET['view'] == 'hierarchy'): ?>
        <?php echo $this->partial('index/browse-hierarchy.php', array('simplePages' => get_simple_pages_for_loop())); ?>
    <?php else: ?>
        <?php echo $this->partial('index/browse-list.php', array('simplePages' => get_simple_pages_for_loop())); ?>
    <?php endif; ?>  



***********************
Building Forms in Admin
***********************

Omeka 2.0 admin interface works with modern CSS and design practices, including responsive design. Omeka 2.0 therefore also includes a :php:class:`Omeka_Form_Admin` class to help you quickly and easily build simple forms. It should be suitable for building basic add/edit forms. The SimplePages plugin makes uses it, can can offer a good example of usage.

It is best to put your form-building logic into your controller, e.g. in a ``_getForm()`` method. The :php:class:`Omeka_Form_Admin` class works basically as follows.

If you are editing an existing record, instantiate it like so: ``$form = new Omeka_Form_Admin(array('record'=>$record);``

By default, if you pass in a record the form will assume that you want a link to the record's public page. If not pass in an array like ``array('record'=>$record, 'hasPublicPage'=>false)``

Otherwise, you need not pass any argument.

To add your form elements to the main editing area, use :php:meth:`Omeka_Form_Admin::addElementToEditGroup`. You can either pass in a ``Zend_Form_Element`` you have already built, or pass in the parameters to build the element as if you were creating one. For example, creating a text input looks like this:

.. code-block:: php

     $form->addElementToEditGroup('text',
         'title',
         array(  'id'=>'simple-pages-title',
                 'size'  => 40,
                 'value' => metadata($page, 'title'),
                 'label' => 'Title',
                 'description' => 'The title of the page (required).',
                 'required' => true
         ));

The first argument specifies the element type (text, textarea, etc.). The second gives the name to be used on the element in the form. The third gives a keyed array of various attributes for the element, as well as a label and a description.

If you build the Zend_Form_Element yourself, you can simply pass that in as the first parameter and leave the rest empty.

In some cases, it makes sense to add an element directly to the save panel on the right. This should be reserved for small, peripheral data, such as whether a record is public or featured, if the model implements those features.

Doing so works similarly, using the :php:meth:`Omeka_Form_Admin::addElementToSaveGroup` method:

.. code-block:: php

        $form->addElementToSaveGroup('checkbox', 'is_published',
            array('id' => 'simple_pages_is_published',
                 'values' => array(1, 0),
                 'checked' => metadata($page, 'is_published'),
                 'label' => 'Publish this page?',
                 'description' => 'Checking this box will make the page public and it will appear in Simple Page navigation.'
            ));

As with ``addElementToEditGroup()``, you can build the element yourself and pass it as the first parameter.

For more complex form requiring tabs and a variety of sections, you'll want to familiarize yourself with :ref:`understanding_the_admin_css`.


